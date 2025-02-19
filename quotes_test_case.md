# Feature: Test Scenarios for New Quotes Design  

## Version: 0.0.53
## Author: QA Team
## Date: 2/13/2025 - 2/18/2025
## Test Manager: Nabina Mainali
## Environment: Staging
## Scope: Functional Testing

## Overview  
This document outlines the test scenarios for the new design of Quotes feature.  


## **Negative Test Scenarios**

**Note: Analysis to be done**
## **Scenario 1.1.1: The system should prevent adding duplicate items to Quotes**
**Given** the traveller has already saved an item to Quotes  
**When** they attempt to add the same item again  
**Then** the system should display a message "Item already added to Quotes"   

---

**Note: To be implemented**
## **Scenario 1.1.2: If the internet disconnects while saving a Quote, the system should handle it properly**
**Given** the traveller adds an item to Quotes  
**When** they click "Save to Quotes" and lose internet connection  
**Then** the system should show an error "Unable to save Quote. Please check your connection" 

---

## **Scenario 1.1.3: Traveller should see an empty state message if no quotes are saved**
**Given** the traveller has no saved Quotes  
**When** they open the Quotes section  
**Then** a message like "No saved quotes yet" should be displayed  

---

## **Scenario 1.1.4: Traveller should not be able to proceed checkout leaving any required input field empty**
**Given** the traveller is editing details of the saved Quote  
**When** they leave any required input field (e.g., gender, mobile phone, pickup location) empty  
**Then** the system should prevent checkout and prompt to complete missing fields

---

## **Scenario 1.1.5: Traveller should not be able to save invalid details in the details of a Quote**  
**Given** the traveller is entering details in the cart of Quotes section  
**When** they input invalid details (e.g., an incorrect phone number format 00000)  
**Then** the system should display a validation error and prevent saving the invalid data

---

## **Scenario 1.1.6: Traveller should not be able to save incorrect changes in the details of a Quote**  
**Given** the traveller is editing details of the saved Quote  
**When** they enter invalid details (e.g., an incorrect phone number format 00000)  
**Then** the system should display a validation error and prevent saving the invalid data

---

## **Scenario 1.1.7: Traveller should not be able to add negative numbers in the guests field**
**Given** the traveller is editing details of the saved Quote  
**When** the traveller try to decrement the guest count below 1  
**Then** the count should not go below 1

---

## **Scenario 1.1.8: Traveller should not be able to proceed with purchase until at least one traveller’s detail is provided**
**Given** the traveller has items in Quotes  
**When** they proceed to checkout without entering any traveller details  
**Then** the system should prevent purchase

---

## **Scenario 1.1.9: Traveller should not be able to save invalid details in "Add my Details" and "Add Another Traveller"**  
**Given** the traveller is entering details in "Add my Details" and "Add Another Traveller"  
**When** they input invalid details (e.g., name: $$$$, phone number: 1234, 0000)  
**Then** the system should show a validation error and prevent saving 

---

## **Scenario 1.1.10: System should not allow saving an overly long name in traveller details**
**Given** the traveller is entering details in "Add My Details"  
**When** they input a name exceeding the character limit (e.g., 200+ characters)  
**Then** the system should show a validation error and prevent saving

---

## **Scenario 1.1.11: System should not allow saving special characters in name fields**
**Given** the traveller is entering details in "Add My Details"  
**When** they input special characters (e.g., "John@Doe!") in the name field  
**Then** the system should show a validation error and prevent saving

---

## **Scenario 1.1.12: Traveller should not be able to save the details without entering all required fields**
**Given** the traveller is adding details in "Add my Details"  
**When** they leave a required field (e.g., country) empty  
**Then** the system should prevent saving

---

## **Scenario 1.1.13: Traveller should not be able to proceed with purchase if additional traveller details are required but not provided**
**Given** the traveller is adding additional traveller details  
**When** the form is left empty  
**Then** the purchase button should not be enabled

---

## **Scenario 1.1.14: Traveller must accept booking terms and conditions to pay by credit card**
**Given** the traveller is on purchase screen  
**When** they have not checked "I accept the bookings terms and conditions"  
**Then** the "Pay now by credit card" button should remain disabled

---

## **Scenario 1.1.15: System should not allow saving an expired payment method**
**Given** the traveller is entering payment details  
**When** they input an expired credit card  
**Then** the system should show an error message "Card is expired" and prevent payment

---

**Note: Analysis to be done**
## **Scenario 1.1.16: Prevent using a Quote that has passed its validity period**
**Given** the traveller has a saved Quote with an expiration date  
**When** they attempt to use it after the expiry date  
**Then** the system should prevent checkout and display "This Quote has expired"  

---

## **Positive Test Scenarios**

## **Scenario 1.1.17: Quotes should be retained after logging in again**  
**Given** the traveller has saved Quotes  
**When** they log out and log in again  
**Then** the Quotes should still be available in the Quotes section   

---

## **Scenario 1.1.18: Saved items should be visible in the Quotes section**  
**Given** the traveller has added items to Quotes  
**When** they open the Quotes section  
**Then** the items should be displayed  

---

## **Scenario 1.1.19: Traveller should be able to delete a saved Quote**  
**Given** the traveller has saved Quotes  
**When** the traveller clicks on "Delete"  
**Then** the quote should be removed from the list   

---

## **Scenario 1.1.20: Traveller should get a confirmation message while deleting a saved quote**
**Given** the traveller has saved Quotes  
**When** the traveller clicks on "Delete"  
**Then** a confirmation popup should be displayed to confirm deletion

---

## **Scenario 1.1.21: Traveller should remain on the same screen when selecting "NO" in the delete confirmation popup**
**Given** the traveller has a saved Quote and attempts to delete it  
**When** the delete confirmation popup appears  
**And** the traveller selects "NO"  
**Then** the system should close the popup  
**And** the traveller should remain on the same screen without deleting the Quote

---

## **Scenario 1.1.22: Traveller should see the correct products details in the "Open Details"** 
**Given** the traveller is in quotes page  
**When** the traveller clicks on "Open Details"  
**Then** the correct details of the items which were saved to the quotes should be shown

---

## **Scenario 1.1.23: Items should be removable from the cart**
**Given** there are multiple items in the cart  
**When** the traveller removes an item  
**Then** the items should be removed successfully

---

## **Scenario 1.1.24: Traveller should see the updated total price after removing any items in Quotes**
**Given** the traveller has multiple items in the cart of Quotes section   
**When** they remove an item from the cart  
**Then** the total price should update correctly across all pages (e.g., Purchase, Checkout, Payment)

---

## **Scenario 1.1.25: Traveller should be able to proceed checkout with optional input fields empty**
**Given** the  traveller is editing details of a saved Quote  
**When** they leave all optional fields (e.g., gender, mobile phone, pickup location) empty  
**Then** the system should allow them to proceed to checkout

---

## **Scenario 1.1.26: Traveller should be able to proceed checkout after filling optional input fields**
**Given** the traveller is editing details of a saved Quote  
**When** they fill in all optional input fields (e.g., gender, mobile phone, pickup location)  
**Then** the system should allow them to proceed to checkout

---

## **Scenario 1.1.27: Traveller should be able to proceed to checkout after filling up valid details**
**Given** the traveller opens the details of items in Quotes  
**When** they enter valid details and click checkout  
**Then** the checkout button should be enabled

---

## **Scenario 1.1.28: Saved traveller details should be prefilled in the checkout form**
**Given** the traveller has entered their details previously  
**When** they reach the checkout screen  
**Then** the details form should be prepopulated with their saved information

---

## **Scenario 1.1.29: Traveller should be able to edit saved details in the Checkout section**
**Given** the traveller has already saved their details in a Quote  
**When** the traveller proceeds to the Checkout section and edits their details  
**Then** the updated details should be saved successfully

---

## **Scenario 1.1.30: Traveller should be able to add another traveller's details**
**Given** the traveller wants to add another traveller  
**When** they fill in the details  
**Then** the system should allow saving the additional traveller's details

---

## **Scenario 1.1.31: Traveller should receive an email confirmation after successfully completing a purchase from Quotes**
**Given** the traveller has successfully completed the payment for a saved Quote  
**When** the payment is processed and confirmed  
**Then** the system should send an email confirmation to the traveller  
**And** the email should include the booking details, payment summary, and confirmation number

---

## **Scenario 1.1.32: Quote items should be moved to Bookings after successful payment**
**Given** the traveller has successfully completed the payment for a saved Quote  
**When** the payment is processed and confirmed  
**Then** the system should move the purchased items from Quotes to the Bookings section  
**And** the traveller should be able to view the booking details under their Bookings

---
