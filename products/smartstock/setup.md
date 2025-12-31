# Setup

## Setting up a new product

It's super easy to set up a new product, no EANs or making tools into models.. None of that, please.

1. Locate the Products folder.\
   ![](<../../.gitbook/assets/image (42).png>)
2. You'll find that Bloxy Cola has already been set up. Don't delete it first until you reached the end of the setup.
3. Insert a new folder into the Products folder. You can rename it to whatever name you want.\
   ![](<../../.gitbook/assets/image (45).png>)
4. Insert the tools for the product and position them however you like. The system will automatically remove `TouchTransmitter`s and ensure that the tool will still function how you want it to when it's taken by a Player.
5. Create a new **invisible** part called "PromptPart" and anchor it. This part is where the prompt to take/return the product will be.
6. That's it, you have just made your first product!



## Overriding default maximum quantity

To override the system's maximum quantity for a product:

1. Locate the product's folder in Products.\
   ![](<../../.gitbook/assets/image (18).png>)
2. Create a new attribute in the product's folder called "SS\_MaximumQuantity" and set the type to `number`.
3. Set the attribute's value to any number you'd like.
