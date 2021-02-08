# Post #100DaysOfCode Log - Dashiell Bark-Huss

I completed my 365 days of code in 2019. I logged my progress everyday. I continued to add to my [2020 log](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md). This is my 2021 log.

<hr>
<h3 id="update-1-29-21"></h3>

## Building [WishTender](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-9-16-20) Update - Sunday 2/7/21

<hr>

## Most People Can't Get Through The Hardest Part Of A Goal

It's been 7 months and 2 weeks since WishTender was an idea. 6 months and 4 weeks since I made a demo of the app. 6 months and 3 weeks since I started coding the app.

When I started my spouse asked me when I'd be done. I said by the end of October. That was 3 months ago.

I'm not surprised it's taking me longer. I'm building a full app myself for the first time. I have to remind myself, it's only been 768 days since I started my [first day](https://github.com/DashBarkHuss/100-days-of-code/blob/master/r1-log.md#r1d1---1119) of #100DaysOfCode.

So I'm not here to complain about the length of time it's taking me.

I'm at a point though where the excitement of starting the project is wearing off. This is the point I believe where most people struggle. The boring part where you're pretty far from the newness, and pretty far from the home stretch. It's going to take patience and persistance to get though this.

## Do What Most People Don't Do

But I can't just rely on "persistence". I've found that forceful modes like persistence and discipline don't work as well as intrinsic motivation, even for people like me who have seemingly endless amounts of willpower. We can try to "discipline" ourselves to the finish line but we often pay the price- usually our health will suffer from the hormonal effects of extreme discipline.

So I need a tactic- beyond willpower- to get through this hump. What got me excited in the first place? That excited is what I need back.

Seeing myself as the founder of a profitable company.

Seeing myself making money.

Seeing myself making enough money to fund lucid dream research and technology.

I shouldn't be ashamed to get too grand with it- Why not see myself on the cover of Wired Magazine? _Meet Dashiell Bark-Huss: The Entreprenuer Who Tweets From Her Dreams And Put $1 Billion Into Lucid Dream Research_

These are the grand delusions that I normally try to tone down. After all, it's more important to get to the blood and sweat- the coding the, market research, the work- than get swept away with day dreams. Or so I thought. I'm seeing instead, that we need a balance of the grand delusions and the hard work. Contrary to what "Discipline Dashie" believes, "Delusion Dashie" runs the show. My grand delusions are magic fuel.

## The Magic Fuel

What do I mean these delusions are magic fuel? I've been experimenting. I've found that after I visualize or journal how exciting the future might be, it feels like I instantly gain 15 IQ points and drank a cup of coffee. Much of my very real lethargy and difficulties go away completely after I rejuvenate my excitement for the future.

What are the visualizations I'm doing? Well, I haven't been so prescriptive with it. It's just something I've been dabbling with. For example, I tried the written equivalent of creating a vision board: Journaling why I'm building WishTender, what it will do for my life and other people. I also collected some pictures on instagram of others in similar positions to where I want to be. I updated my linked in with "_Technical Founder at WishTender_" to remind myself this is real and give myself a bit of public accountability.

Now that I'm seeing necessity and benefits of visualizations, I may be a bit more prescriptive. So many self help book say to do some form of visualizations or goal reciting before work (The One Thing, The Miracle Morning, Think And Grow Rich). When you get far enough into a project this becomes so important. You have to keep that intrinsic motivation going. Other people aren't going to do be your cheerleader. Most probably don't have the patience for their own projects, they certainly won't have the patience for yours. So be unique. Be persistent, be patience, and have grand delusions.

<hr>
<h3 id="update-1-29-21"></h3>

## Building [WishTender](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-9-16-20) Journey - Friday 1/29/21

<hr>

Resources to save:
[Node Checkout example](https://github.com/pararell/eshop-angular-node/blob/b9b5c7fffaef797f84a7c79d7f658a30e1bed9cc/routes/billingRoutes.ts)

<hr>
<h3 id="update-1-29-21"></h3>

## Building [WishTender](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-9-16-20) Journey

## Answers to My App Architecture [Question](#update-1-28-21)

### Friday 1/29/21 - Thursday 1-28-21

<hr>

After my [question](#update-1-28-21) yesterday I got a lot of helpful responses.

## [Theo Khayat](https://www.linkedin.com/in/theokhayat/) on LinkedIn

> You're looking for some all-or-nothing processing(checkout AWS step functions - am not recommending specifically AWS, just as an example of chaining multiple backend events) as this allows your frontend to request a single endpoint, and subsequently know if ALL the backend events succeeded or not, in a single status code. Hope that helps and best wishes :)

Theo introduced me to the term **all-or-nothing processing**. I googled **all-or-nothing processing** which lead me additional useful terms like **batch** and **bulk** requests. It lead me to better worded questions than my own like "How do I perform different actions on resources of different types in one request?"

Sometimes when I'm stuck it's because I don't know the correct terms or questions to ask. Reaching out for help can introduced me to terms and well-worded questions that will get me on track.

## [Ryan Lynch @joyofui](https://twitter.com/joyofui) on Twitter

> My answer to your question, which I'd sum up as "What do I do when an endpoint doesn't map to REST", would be : not everything has to be RESTful in your API. REST and is just one way of slicing things up. Maybe think of some endpoints as REST, some as just RPC's like "doCheckout"

Me:

> Yes, you phrased my question better than I did. A lot of my questions lately have surrounded this idea- that you do not alway have to follow REST. As a newbie it's been a bit confusing trying to understand when to break a convention. Thanks for bringing RCP to attention.
>
> I should say when and how to break convention
>
> _[This part was in a DM in a related conversation:]_ When I was more of a newbie there usually was one best way. But it seems as you progress to more advanced things there are less best practices. But it's interesting to see how other developers think through the problem

[Ryan Lynch @joyofui](https://twitter.com/joyofui):

> A rule of thumb is, if you are creating either more work or more mental overhead to build or understand the code, think about changing conventions or breaking them all together. Not all problems are generic and have generic solutions, so don't be bound to generic answers!

This last remark by Ryan hits on a problem I see with myself and other newbies- fear of breaking convention. Often times it isn't even clear to a newbie when something is a flexible convention, and when it is a serious rule that you should never break.

I looked into other forms of API's after Ryan suggested RPC.

Video: [Nate Barbettini – API Throwdown: RPC vs REST vs GraphQL, Iterate 2018](https://www.youtube.com/watch?v=IvsANO0qZEg)

In this video Nate illustrates why you might break a convention for another API convention that fits your use case. It may be more important for one project that the API is highly flexible and documented, REST is great here. But I'm building a private API so I may value low chattiness over flexibility.

## [Helge Drews @helgedrews](https://twitter.com/helgedrews) on Twitter:

> I think what you're searching for is a CheckoutController and not CheckoutService. Simply said, you inject all your Services into it and the Controller orchestrates all the business logic, handles Errors and so on. Put it behind the POST /checkout route. :)

My Response:

> Thanks helge, I had a checkout route (the equivalent of a controller?) but it was getting big and I though it was considered a best practice to leave fat business logic out of the controller and move it to a service, so I also made a service. Not sure if that makes sense

Before I sent that last response, **Helge** sent me a DM to elaborate:

> Here I've got some more infos to the answer in your twitter thread about how to organize your app architecture.
>
> in the root file app.js you can do something like this:
>
> ```javascript
> const checkoutController = new >CheckoutController({
>    emailService,
>    orderRepository,
>    paypalService,
>    productRepository,
>    shopConfigRepository,
>    shoppingCartRepository,
>    stripeService
> });
> // ...
> app.use('/checkout/', >checkoutController.router);
>
> CheckoutController looks like this:
> export default class >CheckoutController {
>    constructor({
>        emailService,
>        orderRepository,
>        paypalService,
>        productRepository,
>        shopConfigRepository,
>        shoppingCartRepository,
>        stripeService
>    }) {
>        // Routes
>        this.router = new Router();
>        http://this.router.post('/prepare', async (req, res, next) => this.prepare(req, res, next));
>        http://this.router.post('/complete', async (req, res, next) => this.complete(req, res, next));
>
>        // Repo
>        this.orderRepository = orderRepository;
>        this.productRepository = productRepository;
>        this.shoppingCartRepository = shoppingCartRepository;
>        this.shopConfigRepository = shopConfigRepository;
>
>        // Service
>        this.emailService = emailService;
>        this.paypalService = paypalService;
>        this.stripeService = stripeService;
>    }
>
> // the implementation of the methods >behind the routes and a lot  of other >helper methods
> ```

Helge used the terms "repository" and "controller" which introduced me to the **Repository-Service pattern**.

## [John Zhao](https://www.linkedin.com/in/john-zhao-3136647b/) on LinkedIn:

> one endpoint can interact with many services and models. that's the entire point of the backend - to glue all the different pieces together.
>
> the vast majority of backend code in the real world is never as simple as one route -> one service -> one model. taking your example of getting a product from a database, in the real world, you'll probably want to call one endpoint to get the product info, product upsells and product reviews that are stored in different models.
>
> just google node ecommerce projects on github and you'll find plenty of examples to guide you

Many tutorials simplify projects so we rarely see these more complex real world backends. Finding more complex examples is important.

It seems obvious, but I hadn't thought to search for the term "ecommerce", I kept searching for "shop". That small suggestion was helpful.

### Thanks to everyone who helped!

<hr>

## Random/Messy Notes and Resources

As I was reading guidance from the helpful people above, I did some googling and note taking:

https://apihandyman.io/api-design-tips-and-tricks-getting-creating-updating-or-deleting-multiple-resources-in-one-api-call/

> What if I want to do DELETE /resources/ID1 and PATCH /another-resources/ID2 at the same time?
>
> This is really nasty and definitely not REST, but it can be useful for backend for frontend or experience API for example.
>
> To do that we’ll need to POST data on a specific endpoint which could something like /batch, /bulk or even / and we will have to add a uri and replace the id value by something provided by the consumer:
> Actions number 1 is DELETE /resources/ID1 and its result will be identified in the 207 response by the id ACTION1.
>
> To see a complete example you should take a look at Facebook’s Graph API batch endpoint documentation. Note that this batch endpoint match request/response based on index and does far more than just processing a bunch of request.

https://www.codementor.io/blog/batch-endpoints-6olbjay1hd

> Google has implemented a complicated but flexible batch endpoint. Instead of having an endpoint that accepts multiple resources, there's an endpoint that accepts multiple requests. These are essentially "meta" HTTP requests, where the main request contains different sub-requests.

[Nate Barbettini – API Throwdown: RPC vs REST vs GraphQL, Iterate 2018](https://www.youtube.com/watch?v=IvsANO0qZEg)

[Best Practices for Building API Integrations](https://blog.bearer.sh/api-integration-best-practices/)

> The difference between an API and an integration is that an API integration is how your application connects to an API.

<hr>
<h3 id="update-1-28-21"></h3>

## Thursday 1-28-21

## [WishTender](https://github.com/DashBarkHuss/100-days-of-code/blob/master/post-log.md#update-9-16-20) Code Notes:

<hr>

I've been confused about app architecture when your app gets complex.

**It's easy when the routes map simply to a resource.**

For example, **adding a product to a shop.**

In this case you might have a

- `Product.Model.js`- a mongoose model. This is your resource.
- `ProductService.js`- a service that interacts with that model.
- `product.js`- a router that directs the express app based on different routes like `GET /product/213`. The routes tells the app which service to use and what the response should be.

Thats simple.

**But what about something not so straight forward?**

**For example, what route, service, and resource do we use when a client checks out?** There isn't one clear resource here. When a client checks out we are interacting with many resources and services.

These might be:

- The `Order.Model.js`, a mongoose model that stores order information such as cart items, time purchased, and currency conversions.
- The shop owner's account `Owner.Model.js` because we might want to track their earnings on their account.
- 3rd party API's, like Stripe for payment processing.
- An email service- `Email.Service.js`- to send a reciept to the buyer and a notification to the shop owner.

and on and on...

In this case should we make a `checkout.js` route that maps `POST /checkout` to a `CheckoutService.js`?

`CheckoutService.js` could then interacts with many services and resources like

- `StripeService.js`
- `OrderService.js`
- `OwnerService.js`
- `EmailService.js`

Is this how it should be done?

**A little more simply, what about when we're just creating a resources on a third party?** For example a Stripe Connect account. Stripe Connect accounts: when you use Stripe as a marketplace, your platform has an account with Stripe and your users- like shop owners- have their own accounts called Connect accounts, connected to your platform account.

Your users need to create these Connect account. What route do you use? What service do you use?

It's not as simple as `blogRoute.js`--> `BlogService.js` -->`Blog.Model.js`. You don't house the resource on your site, the connect account object is housed on Stripe.

You might also create a model, `StripeAccountInfo.Model.js` to house some information about the account that is pertinent to your app- like currency, if the user paid their monthly fees to cover the Stripe Connect fees, and Stripe account number. But now, you have a resource on your site _and_ a resource on stripe that need to be interacted with. How will this look like in your app architecture?

## Help Me!

These are some things I've been confused by. I rarely see any information on these more complex circumstances. **If any one has any resources, answers, is willing to talk it out over the phone, or even clues to what I should google I'd love to hear from you.**

Twitter: [@DashBarkHuss](https://twitter.com/DashBarkHuss)

LinkedIn: [in/dashbh/](https://www.linkedin.com/in/dashbh/)

<hr>
<h3 id="update-1-21-21"></h3>

## Thursday 1-21-21

I reviewed circuit basics [Lesson 1 - Voltage, Current, Resistance (Engineering Circuit Analysis)
](https://www.youtube.com/watch?v=OGa_b26eK2c) - really nice explanation of circuit basics.

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
