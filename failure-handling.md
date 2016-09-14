# Handling Errors

## Context:

To date our primary focus has been on basic (or tokenized) card payments. For this payment method, failure handling turns out to be trivial because no funds have changed hands as a result of API flow and in all cases the repercussions of not handling failures are negligible. However, it appears that many other Payment Methods are characterized by or differentiated by some form of payment processing where funds have or will exchange hands. In these cases the repercussions of not handling failures gracefully are much more severe and can include things like duplicate payments or orphaned partially completed payments.

Let's consider the following sequence of events as a running example:

1. Payee constructs a PaymentRequest and transfers it to the Payment Mediator
2. Payment Mediator passes the PaymentRequest to the user-selected Payment App
3. The Payment App returns a PaymentResponse to the Payment Mediator
4. The Payment Mediator returns the PaymentResponse to the Payee
5. Payee handles the PaymentResponse in some persistent way

These steps do not capture the entirety of interactions performed in the lifecycle of the Payment Request spec, but do they highlight a number of critical points in the algorithm. If we are unable to gracefully handle failure in between any two of these steps then we risk funds exchange hands improperly.

## Why is this an API problem?

One could go down the route of saying that failure handling is a task that the Payment App must address. This approach will necessarily fracture the Payment App ecosystem as each new Payment Method invents its own solution. With every Payment App implementing its own proprietary solution, Payment Methods become all the more coupled with Payment Apps which limits the developer's agility in supporting new payment methods and in turn limits the utility of reusable apps to the end user.

## What do we have today?

The best practices spec (https://w3c.github.io/webpayments/proposals/method-practice/#network) mentions failures should be handled and gives some loose suggestions.

The specs below both involve payment processing, but do not mention how errors should be handled at any critical boundary.

* http://w3c.github.io/webpayments-methods-credit-transfer-direct-debit/
* https://w3c.github.io/webpayments/proposals/Alipay-payment-method.html

## Next Steps:

At TPAC we have a breakout session dedicated to the topic of "Push Payments and Failure Handling". I believe we should use this session to define how much error handling we want to be within scope for the Payment Request API and why. In any case, I think we should strive to add error handling detail to the SEPA Credit Transfer and Alipay specs.
