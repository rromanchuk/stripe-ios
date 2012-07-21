This SDK allows you to charge credit cards on an iOS 5 device using the Stripe API.

Usage is a simple asynchronous call:
```
#import "Stripe.h"

StripeConnection *stripe = [StripeConnection connectionWithPublishableKey:@"pk_dl4LcpeAxUEPHN3FxzuAQQmhCGmx5"];

StripeCard *card =  [[StripeCard alloc] init];
card.number =       @"4111111111111111";
card.name =         @"Bob Dylan";
card.securityCode = @"010";
card.expiryMonth =  [NSNumber numberWithInteger:2];
card.expiryYear =   [NSNumber numberWithInteger:2014];

[stripe performRequestWithCard:card 
                 amountInCents:[NSNumber numberWithInteger:200] 
                       success:^(StripeResponse *token) 
     {
         /* handle success */
     }
                         error:^(NSError *error) 
     {
         /* handle failure */
     }];
```
Please build the "example" target for an example of it in action.
