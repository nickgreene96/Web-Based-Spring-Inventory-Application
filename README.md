WESTERN GOVERNOR UNIVERSITY
## D287 – JAVA FRAMEWORKS
C.  Customize the HTML user interface for your customer’s application. The user interface should include the shop name, the product names, and the names of the parts.


---using "MainScreenController", I am going to customize the theme for this online shop. In this case it will be computers








Note: Do not remove any elements that were included in the screen. You may add any additional elements you would like or any images, colors, and styles, although it is not required.








D.  Add an “About” page to the application to describe your chosen customer’s company to web viewers and include navigation to and from the “About” page and the main screen.


-- talked about the companies mission statement. Added a "return to maincreen" button at the bottom of the about page.
And inserted the link at the bottom of the main page.




E.  Add a sample inventory appropriate for your chosen store to the application. You should have five parts and five products in your sample inventory and should not overwrite existing data in the database.


-- created "setInvMax" & "setInvMin" in the "Part.java" class
-- the 5 parts: case , motherboard , graphics card , cpu , ram
-- 5 products: tablets , surface-laptops , mini-desktops , average desktop, gaming desktop




Note: Make sure the sample inventory is added only when both the part and product lists are empty. When adding the sample inventory appropriate for the store, the inventory is stored in a set so duplicate items cannot be added to your products. When duplicate items are added, make a “multi-pack” part.








F.  Add a “Buy Now” button to your product & part list. Your “Buy Now” button must meet each of the following parameters:
•  The “Buy Now” button must be next to the buttons that update and delete products.
•  The button should decrement the inventory of that product by one. It should not affect the inventory of any of the associated parts.
•  Display a message that indicates the success or failure of a purchase.


-- added the “Buy Now” button, as well as the controller for it's functions.
- the CONTROLLER holds the redirecting for the success/fail scenario.


--I also created two pages for purchase success/fail, displaying an appropriate message




G.  Modify the parts to track maximum and minimum inventory by doing the following:
•  Add additional fields to the part entity for maximum and minimum inventory.
•  Modify the sample inventory to include the maximum and minimum fields.
•  Add to the InhousePartForm and OutsourcedPartForm forms additional text inputs for the inventory so the user can set the maximum and minimum values.
•  Rename the file the persistent storage is saved to.
•  Modify the code to enforce that the inventory is between or at the minimum and maximum value.


-- created the "maxInventoryError" & "minInventoryError" input values in both the "InhousePartForm.html"(line24) & "OutsourcedPartForm.html"(line25) files
-- Created the int variables "maxInv" & "minInv" in the "Part.java" class. Used to send back the part with the smallest inventory
-- I have added the "minInv" & "maxInv" variable to the 2 "Part" constructors in the "Part.java" class on lines 51 & 59
-- Created the method "getMinInv()" & "setMinInv()" in the "Part.java" class that wil get and return the minimum int that the inventory can have on line 93
-- Created the method "getMaxInv()" & "setMaxInv()" in the "Part.java" class that wil get and return the maximum int that the inventory can have
!           !
-- changed the name of the database IN "FILE EXPLORER" from "spring-boot-h2-db102.mv" to "database.mv"
-and changed the name in the "application.properties" file from "spring-boot-h2-db102" to "database"
!                       !


H.  Add validation for between or at the maximum and minimum fields. The validation must include the following:
•  Display error messages for low inventory when adding and updating parts if the inventory is less than the minimum number of parts.
•  Display error messages for low inventory when adding and updating products lowers the part inventory below the minimum.
•  Display error messages when adding and updating parts if the inventory is greater than the maximum.


-- Changed the if statement on line 37, in file "EnufPartsValidator.java" to include "|| (p.getInv() - product.getInv()) < p.getMinInv()" at the end.
-- using a built in validator in the "Part.java" class, on line 33 to set a maximum
and output a message

J. - added two  unit test “testMax()” & “testMin()” to PartTest 

I. commented out the “DeletePartValidator”
