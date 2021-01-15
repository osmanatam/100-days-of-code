# Post #100DaysOfCode Log - Dashiell Bark-Huss

I completed my 365 days of code in 2019. I logged my progress everyday. I continued to add to my [2020 log](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md). This is my 2021 log.

<hr>
<h3 id="update-1-15-21"></h3>

## Friday 1-15-21

## [WishTender](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-9-16-20) Code Notes:

<hr>

## Data Transformation Between Backend and Frontend

Working with the data in your app can be confusing when the data needs to be transformed into different representations.

## Prices

Like prices.

- When you **display** prices they will look like **$5,000.00**. This will change depending on the currency.
- When the user **inputs** a price it might look like **5000**, **5,000**, **5000.00**, **5.000,00** .
- And when you do calculations with prices you usually work in integers so **$5,000.00** would be **5000000** pennies.

Keeping track of all these different formats can be confusing. How should we ultimately store prices in the database? When do these transformations happen from database format to view format and back?

## Front to Back

I [asked](https://stackoverflow.com/questions/65707764/where-should-data-be-transformed-for-the-database) on StackOverflow:

> Where should data be transformed for the database?

The answers showed there isn't one standard way. While sanitization happens on the backend for security reasons, normalization can happen in either place. People gave good ideas for how to decide. Check out the answers by [@nickang](https://twitter.com/nickang), [@helgedrews](https://twitter.com/helgedrews), and [Cosmin Ioniță](https://stackoverflow.com/users/2787364/cosmin-ioni%c8%9b%c4%83) on stackoverflow [here](https://stackoverflow.com/questions/65707764/where-should-data-be-transformed-for-the-database#answers).

My question asked about transformations from the frontend user input to the backend. But I also wonder about transformations happening when data is sent from the backend to the frontend.

## Both Back to Front and Front To Back

This answer suggests that the conversions should happen at the boundaries of the app.
[Unit conversion of data](https://softwareengineering.stackexchange.com/questions/391474/unit-conversion-of-data):

> Keep consistent units within your system, and only convert to the user's preferred format at the boundaries of your system. The “boundary” doesn't necessarily mean front-end or back-end, this is more about how you structure the logic in your application. A classic MVC application would convert incoming data in the controllers, and outgoing data in the views.

I'm not sure if "incoming data" here means to the server or to the client. I'm going to assume incoming means from the frontend to the backend.

## What Format to Store in the database?

The same answerer above suggested:

> Keep consistent units within your system...
>
> Do not store the data in multiple formats in the database. This makes it so much harder to keep the various versions of the data consistent, and will make queries more complicated. Internally, your system should define a single authoritative data model.

I found a lot of ways people store price in the database, but the most common was to store price as an integer- the smallest unit of the currency. Here [@helgedrews](https://twitter.com/helgedrews) points to other API's for inspiration:

> Furthermore, it can be helpful to take a look at some different APIs of well-known providers and how these handle prices.
>
> The Paypal API uses an amount object to transfer prices as decimals together with a currency code.
>
> ```json
> "amount": {
>    "value": "9.87",
>    "currency": "USD"
> }
> ```
>
> It's up to you how to handle it in the frontend. Here is a link with an example request from the docs:
>
> https://developer.paypal.com/docs/api/payments.payouts-batch/v1#payouts_post
> Stripe uses a slightly different model.
>
> ```json
> {
>   "unit_amount": 1600,
>   "currency": "usd"
> }
> ```
>
> It has integer values in the base unit of the currency as the amount and a currency code to describe prices. Here are two examples to make it more clear:
>
> - https://stripe.com/docs/api/prices/create?lang=node
>
> - https://stripe.com/docs/checkout/integration-builder
>
> In both cases, the normalization and sanitization has to be done before making requests. The response will also need formatting before showing it to the user. Of course, most of these requests are done by backend code. But if you look at the prebuilt checkout pages from Stripe or Paypal, these are also using normalized and sanitized values for their frontend integrations: https://developer.paypal.com/docs/business/checkout/configure-payments/single-page-app

## Outgoing example

So an outgoing boundary could be in the callback of a HTTP request. Here we do the transformation there before the client displays the data:

```javascript
useEffect(() => {
  if (!cart) {
    fetchGet("/cart", (crt) => {
      parseCartPrices(crt); // parseCartPrices transforms cart prices. ex: 100000 -> "1000.00"
      setCart(crt);
    });
  }
}, [cart]);
```

You could have this transformation go even further, `100000` -> `"$1,000.00"`, or even `100000` -> `"CA$1,800.10 estimated from $1,000.00"`. But I thought leaving it at `"1000.00"` would be more flexible. There are some calculations I do with the prices on the frontend. If the price was in the format `"$1,000.00"` I would have to parse it into `"1000.00"` before doing the calculations. So instead, I will further transform `"1000.00"` to `"$1,000.00"` only where necessary.

## Incoming example

An incoming boundary could be in the `onSubmit` function of a form.

```javascript
const onSubmit = (data) => {
  data.price = toSmallestUnit(data.price, clientCurrency); // toSmallestUnit turns "100.00" into "10000" if currency is USD
  props.onSubmit(data); // props.onSubmit sends the data to the backend in a POST request.
};
```

Alternatively, you could transform `"100.00"` into `"10000"` just on the other side of the boundary in the backend, for example using an `express-validator` `customSanitizer`.

<hr>
<h3 id="update-1-11-21"></h3>

## Monday 1-11-21

## [WishTender](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-9-16-20) Code Notes:

<hr>

## Handle Validations before logic:

> You can handle some validations in your user model using Mongoose. For best practices, we want to make sure validation happens before business logic.

- Shailesh Shekhawat in [How to make input validation simple and clean in your Express.js app](https://www.freecodecamp.org/news/how-to-make-input-validation-simple-and-clean-in-your-express-js-app-ea9b5ff5a8a7/)

## Storing Monetary Value in Database

[What is the best way to store monetary value in a relational database system like MySQL?](https://www.quora.com/What-is-the-best-way-to-store-monetary-value-in-a-relational-database-system-like-MySQL)

[Model Monetary Data](https://docs.mongodb.com/manual/tutorial/model-monetary-data/)

[Storing prices in SQLite, what data-type to use?](https://dba.stackexchange.com/questions/15729/storing-prices-in-sqlite-what-data-type-to-use)

## Transforming data on Back or Front end?

Should I be serving price data up as integers, the way it's stored in my database (_ex instead of $100.00, serve it as 10000_)? The the front end has to transfrom it from 10000 to $100.00. Or should I transform it to $100.00 on the back end and serve that?

It gets more complicated when we take price conversion into account. If the client is in EUR and the price is in USD we have to do an estimate in the UI (_ex "€120 estimated from $100"_). That means we have to fetch the exchange rate and to the conversion on the frontend.

[Should data transformation be on the front or on the back end in this scenario?](https://softwareengineering.stackexchange.com/questions/400595/should-data-transformation-be-on-the-front-or-on-the-back-end-in-this-scenario)

Very helpful: [When is it appropriate to do calculations in front-end?](https://softwareengineering.stackexchange.com/questions/252224/when-is-it-appropriate-to-do-calculations-in-front-end?newreg=ae510a8f69a4461db58b9a0c24bb8dad). You could see many people diagreed but people gave reasons as to why you would do calculations on the front, back, or both.

[Unit conversion of data](https://softwareengineering.stackexchange.com/questions/391474/unit-conversion-of-data):

> Keep consistent units within your system, and only convert to the user's preferred format at the boundaries of your system. The “boundary” doesn't necessarily mean front-end or back-end, this is more about how you structure the logic in your application. A classic MVC application would convert incoming data in the controllers, and outgoing data in the views.
>
> Do not store the data in multiple formats in the database. This makes it so much harder to keep the various versions of the data consistent, and will make queries more complicated. Internally, your system should define a single authoritative data model.

<hr>
<h3 id="update-1-3-21"></h3>

## Sunday 1-3-21

## [WishTender](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-9-16-20) Code Notes:

<hr>

## Sample Localizational/Internationalization project

I finished my sample [currency i18n](https://github.com/DashBarkHuss/currency_localization_react_express) project. It's a sample project that shows how to set the currency for a user depending on their language preference in their browser `accept-language` header.

<img src = "log_imgs/currency_1-3-21.gif">

I wanted to accommodate different currencies because some of my beta users asked me to. But there was little info on the subject. I figured it out and put this sample together so others can understand how it might be done.

## React Wasted Renders

My app was re-rendering too many times. React doesn't have a solution to figuring out what caused a component to update (if you know of a way let me know). There are some notes in my last log entry ([12-29-20](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-12-29-20)) for some clues on how to do this- profiler, memo, react dev tools. I didn't find that any were very good for seeing why a component rendered. For example, memo only shows what props caused a re-render but not state changes.

So I built my own function to figure out when props or state changed. It doesn't show you when a parent rerender caused a component to rerender but you can figure it out if you use the debugging function in the parent and see that the parent re-renders.

## My own react debugging function

This tells you if a component rendered and if the state or props changed.

It helped me figure out why I had so many re-renders. This function could be more DRY.

### useTraceUpdate

```javascript
import { useEffect, useRef } from "react";
import _ from "lodash";
/**
 * tracks component renders
 * @param {String} component component name ex: App.name
 * @param {Object} props
 * @param {Object} state
 */
export default function useTraceUpdate(component, props, state) {
  const prevP = useRef(props);
  const prevS = useRef(state);
  let render = useRef(0);
  useEffect(() => {
    render.current++;
    console.log(component, "rendered ", render.current, " times");
    if (props) {
      const changedProps = Object.entries(props).reduce((ps, [k, v]) => {
        if (prevP.current[k] !== v) {
          ps[k] = [prevP.current[k], v];
        }
        return ps;
      }, {});
      if (Object.keys(changedProps).length > 0) {
        const displayText = Object.entries(changedProps).map((s) =>
          typeof s[1][0] === "object" && typeof s[1][1] === "object"
            ? `${s[0]} object changed, content of object ${
                _.isEqual(s[1][0], s[1][1]) ? "didn't" : "did"
              }  change ${
                !_.isEqual(s[1][0], s[1][1])
                  ? `from ${s[1][0]} to ${s[1][1]}`
                  : ""
              }`
            : `${s[0]} changed from ${s[1][0]} \nto ${s[1][1]}`
        );
        console.log(
          "r:" + render.current + " info: " + component + " changed props:",
          displayText.join("\n")
        );
      }
    }
    prevP.current = props;
    if (state) {
      const changedState = Object.entries(state).reduce((ps, [k, v]) => {
        if (prevS.current[k] !== v) {
          ps[k] = [prevS.current[k], v];
        }
        return ps;
      }, {});
      if (Object.keys(changedState).length > 0) {
        const displayText = Object.entries(changedState).map((s) =>
          typeof s[1][0] === "object" && typeof s[1][1] === "object"
            ? `${s[0]} object changed, content of object ${
                _.isEqual(s[1][0], s[1][1]) ? "didn't" : "did"
              } change ${
                !_.isEqual(s[1][0], s[1][1])
                  ? `from ${s[1][0]} to ${s[1][1]}`
                  : ""
              }`
            : `${s[0]} changed from ${s[1][0]} \nto ${s[1][1]}`
        );
        console.log(
          "r:" + render.current + " " + component + " changed state:",
          displayText.join("\n")
        );
      }
    }
    if (render.current === 1) {
      console.log("r:" + render.current + ": initial render");
    }
    prevS.current = state;
  });
}
```

How to use `useTraceUpdate`:

```javascript
function WishlistPage(props) {
  const [alias, setAlias] = useState(null);
  const [wishlist, setWishlist] = useState(null);
  const [refreshWishlist, setRefreshWishlist] = useState(null);
  const currentUser = useContext(UserContext);

  const states = {
    alias,
    wishlist,
    refreshWishlist,
    currentUser,
  };

  useTraceUpdate(WishlistPage.name, props, states);

  return <div>... blablabla</div>;
}

export default WishlistPage;
```

### console will look like this

<img src = "log_imgs/useTraceUpdate-1-3-21.png">

<hr>
