# ViArt
This plugin belongs to Lucsonpay payment gateway.

Introduction

This is the readme file for lucsonpay Payment Gateway Plugin Integration for ViArt Php based e-Commerce Websites. 
The provided Package helps store merchants to redirect customers to the lucsonpay Payment Gateway when they choose lucsonpay as their payment method. 
After the customer has finished the transaction they are redirected back to an appropriate page on the merchant site 
depending on the status of the transaction.
The aim of this document is to explain the procedure of installation and configuration of the Package on the merchant 
website.


Installation

- Unzip the files and copy paste the two folder "includes" and "payments" in viart root folder


Configuration

- Log in to the ViArt Admin panel
- In top Menu, from "Settings" click on "Payment Systems"
- Click on "New Payments System"
- Check "Is Active" option
- Enter "Payment System Name"
- In "Payment Url" fill "./payments/lucsonpay.php"
- Choose "Form Submit Method" to "Post"
- In Parameter List Section Add following Parameter with their values

Parameter name = Parameter Source[Parameter type]
1)  invoice = order_id[variable]
2)  item_name = basket[variable]
3)  amount = order_total[variable]
4)  email = email[variable]
5)  channel =  (type just a random number)[constant]
6)  callback_url = [{site_url}order_final.php ][constant]
7)  industry =  (Name of your own choice)[constant]
8)  merchant_id =  (Provided by lucsonpay)[constant]
9)  merchant_key =  (Provided by lucsonpay)[constant]
10) merchant_website =  (Provided by lucsonpay)[constant]
11) transaction_url = Url (For Testing Purpose | For Production Purpose)[constant]
12) name = name[variable]
13) phone = phone[variable]

- Click on Save
- Now from the payment gateway list, locate "lucsonpay" and click on "Final Checkout Page" Link
- In Final Checkout Page link under validation parameters
- Check "Additional Validation" checkbox
- In "Validation Script" enter "./payments/lucsonpay_validate.php"
- Set Order Success Status to "New Order"
- Set Pending Status to "Pending"
- Set Failure Status to "Failed"
- In Final Messages Section , set the messages as per you need on thankyou page.
- Click on Save.

# lucsonpay PG URL Details
	staging	
		Transaction Request URL     => https://uat.lucsonpay.com/crm/jsp/paymentrequest

	Production
		Transaction URL             => https://merchant.lucsonpay.com/crm/jsp/paymentrequest
