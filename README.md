# Ordr.in Python Library

## About

A python library for the ordr.in API
See full API documentation at http://hackfood.ordr.in

## Installation

This library can be installed with npm:

    pip install ordrin

## Usage

### Initialization

```python
import ordrin
ordrin_api = ordrin.APIs(api_key, servers)
```

In the initializer, the second argument sets the servers that API requests will
be sent to, and must be set to either `ordrin.PRODUCTION` or `ordrin.TEST`
(defaults to `ordrin.TEST`).


### Order Endpoints

#### Guest Order

    ordrin_api.order_guest(rid, em, tip, first_name, last_name, phone, zip, addr, city, state, card_number, card_cvc, card_expiry, card_bill_addr, card_bill_city, card_bill_state, card_bill_zip, card_bill_phone, tray=None, addr2=None, card_name=None, card_bill_addr2=None, delivery_date=None, delivery_time=None)

##### Arguments

 - `rid` : Ordr.in's unique restaurant identifier for the restaurant.


 - `em` : The customer's email address


 - `tray` : Represents a tray of menu items in the format '[menu item id]/[qty],[option id],...,[option id]'


 - `tip` : Tip amount in dollars and cents


 - `first_name` : The customer's first name


 - `last_name` : The customer's last name


 - `phone` : The customer's phone number


 - `zip` : The zip code part of the address


 - `addr` : The street address


 - `addr2` : The second part of the street address, if needed


 - `city` : The city part of the address


 - `state` : The state part of the address


 - `card_name` : Full name as it appears on the credit card


 - `card_number` : Credit card number


 - `card_cvc` : 3 or 4 digit security code


 - `card_expiry` : The credit card expiration date.


 - `card_bill_addr` : The credit card's billing street address


 - `card_bill_addr2` : The second part of the credit card's biling street address.


 - `card_bill_city` : The credit card's billing city


 - `card_bill_state` : The credit card's billing state


 - `card_bill_zip` : The credit card's billing zip code


 - `card_bill_phone` : The credit card's billing phone number





###### Either

 - `delivery_date` : Delivery date

 - `delivery_time` : Delivery time


###### Or

 - `delivery_date` : Delivery date




#### User Order

    ordrin_api.order_user(rid, tip, first_name, last_name, email, current_password, tray=None, phone=None, zip=None, addr=None, addr2=None, city=None, state=None, nick=None, card_name=None, card_number=None, card_cvc=None, card_expiry=None, card_bill_addr=None, card_bill_addr2=None, card_bill_city=None, card_bill_state=None, card_bill_zip=None, card_bill_phone=None, card_nick=None, delivery_date=None, delivery_time=None)

##### Arguments

 - `rid` : Ordr.in's unique restaurant identifier for the restaurant.


 - `tray` : Represents a tray of menu items in the format '[menu item id]/[qty],[option id],...,[option id]'


 - `tip` : Tip amount in dollars and cents


 - `first_name` : The customer's first name


 - `last_name` : The customer's last name




 - `email` : The user's email address

 - `current_password` : The user's current password



###### Either

 - `phone` : The customer's phone number

 - `zip` : The zip code part of the address

 - `addr` : The street address

 - `addr2` : The second part of the street address, if needed

 - `city` : The city part of the address

 - `state` : The state part of the address


###### Or

 - `nick` : The delivery location nickname. (From the user's addresses)




###### Either

 - `card_name` : Full name as it appears on the credit card

 - `card_number` : Credit card number

 - `card_cvc` : 3 or 4 digit security code

 - `card_expiry` : The credit card expiration date.

 - `card_bill_addr` : The credit card's billing street address

 - `card_bill_addr2` : The second part of the credit card's biling street address.

 - `card_bill_city` : The credit card's billing city

 - `card_bill_state` : The credit card's billing state

 - `card_bill_zip` : The credit card's billing zip code

 - `card_bill_phone` : The credit card's billing phone number


###### Or

 - `card_nick` : The credit card nickname. (From the user's credit cards)




###### Either

 - `delivery_date` : Delivery date

 - `delivery_time` : Delivery time


###### Or

 - `delivery_date` : Delivery date





### Restaurant Endpoints

#### Delivery Check

    ordrin_api.delivery_check(datetime, rid, addr, city, zip)

##### Arguments

 - `datetime` : Delivery date and time


 - `rid` : Ordr.in's unique restaurant identifier for the restaurant.


 - `addr` : Delivery location street address


 - `city` : Delivery location city


 - `zip` : The zip code part of the address





#### Delivery List

    ordrin_api.delivery_list(datetime, addr, city, zip)

##### Arguments

 - `datetime` : Delivery date and time


 - `addr` : Delivery location street address


 - `city` : Delivery location city


 - `zip` : The zip code part of the address





#### Fee

    ordrin_api.fee(datetime, rid, subtotal, tip, addr, city, zip)

##### Arguments

 - `datetime` : Delivery date and time


 - `rid` : Ordr.in's unique restaurant identifier for the restaurant.


 - `subtotal` : The cost of all items in the tray in dollars and cents.


 - `tip` : The tip in dollars and cents.


 - `addr` : Delivery location street address


 - `city` : Delivery location city


 - `zip` : The zip code part of the address





#### Restaurant Details

    ordrin_api.restaurant_details(rid)

##### Arguments

 - `rid` : Ordr.in's unique restaurant identifier for the restaurant.






### User Endpoints

#### Change Password

    ordrin_api.change_password(email, password, current_password)

##### Arguments

 - `email` : The user's email address


 - `password` : The user's new password




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Create Account

    ordrin_api.create_account(email, pw, first_name, last_name)

##### Arguments

 - `email` : The user's email address


 - `pw` : The user's password


 - `first_name` : The user's first name


 - `last_name` : The user's last name





#### Create Address

    ordrin_api.create_addr(email, nick, phone, zip, addr, city, state, current_password, addr2=None)

##### Arguments

 - `email` : The user's email address


 - `nick` : The nickname of this address


 - `phone` : The customer's phone number


 - `zip` : The zip code part of the address


 - `addr` : The street address


 - `addr2` : The second part of the street address, if needed


 - `city` : The city part of the address


 - `state` : The state part of the address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Create Credit Card

    ordrin_api.create_cc(email, nick, card_number, card_cvc, card_expiry, bill_addr, bill_city, bill_state, bill_zip, bill_phone, current_password, bill_addr2=None)

##### Arguments

 - `email` : The user's email address


 - `nick` : The nickname of this address


 - `card_number` : Credit card number


 - `card_cvc` : 3 or 4 digit security code


 - `card_expiry` : The credit card expiration date.


 - `bill_addr` : The credit card's billing street address


 - `bill_addr2` : The second part of the credit card's biling street address.


 - `bill_city` : The credit card's billing city


 - `bill_state` : The credit card's billing state


 - `bill_zip` : The credit card's billing zip code


 - `bill_phone` : The credit card's billing phone number




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Remove address

    ordrin_api.delete_addr(email, nick, current_password)

##### Arguments

 - `email` : The user's email address


 - `nick` : The nickname of this address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Remove Credit Card

    ordrin_api.delete_cc(email, nick, current_password)

##### Arguments

 - `email` : The user's email address


 - `nick` : The nickname of this address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Get Account Information

    ordrin_api.get_account_info(email, current_password)

##### Arguments

 - `email` : The user's email address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Get All Saved Addresses

    ordrin_api.get_all_saved_addrs(email, current_password)

##### Arguments

 - `email` : The user's email address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Get all saved credit cards

    ordrin_api.get_all_saved_ccs(email, current_password)

##### Arguments

 - `email` : The user's email address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Get an Order

    ordrin_api.get_order(email, oid, current_password)

##### Arguments

 - `email` : The user's email address


 - `oid` : Ordr.in's unique order id number.




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Get Order History

    ordrin_api.get_order_history(email, current_password)

##### Arguments

 - `email` : The user's email address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Get a single saved address

    ordrin_api.get_saved_addr(email, nick, current_password)

##### Arguments

 - `email` : The user's email address


 - `nick` : The nickname of this address




 - `email` : The user's email address

 - `current_password` : The user's current password



#### Get a single saved credit card

    ordrin_api.get_saved_cc(email, nick, current_password)

##### Arguments

 - `email` : The user's email address


 - `nick` : The nickname of this address




 - `email` : The user's email address

 - `current_password` : The user's current password



