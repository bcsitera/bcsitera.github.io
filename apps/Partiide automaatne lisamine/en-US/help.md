# Automatic Batch Assignment

The automatic batch assignment solution allows you to:

* Configure conditions for adding batches to items with a single click during sales, production, or inventory write-offs.

* Set customer-specific expiration date requirements for different items during sales.

## Configuration

To use the solution, you must first configure the settings.

### Location Configuration

First, you need to configure the locations where automatic batch assignment is allowed.

To do this, type Batch Addition Rules Setup into the search bar. In the opened list, you can configure the locations and methods as follows:

* Location Code – select the location from the Locations list.

* Enable Automatic Batch Addition – activates automatic batch addition on sales and production order lines, as well as in the item journal

* Method – defines the method by which batches are added:

	* FIFO – batches are assigned based on the FIFO method (First-In-First-Out).

	* FEFO – batches are assigned based on the FEFO method (First-Expired-First-Out).

   * Customer – batches are assigned based on customer-specific settings.

### Item Card Configuration

If you want to issue items based on customer-specific expiration dates, you need to fill in the following fields on the Item Card under the Sales Calculations tab:

**Item Expiration in Days** – the maximum shelf life of the product (mandatory)

**Item Expiration for Customer** – the maximum shelf life of the product for the customer (mandatory)

**Quarantine Calculation** – if the product cannot be shipped to the customer immediately after production, you can set a buffer period during which it becomes sellable.

### Customer Card Configuration

If you want to issue products to a customer based on predefined expiration dates, you need to define these expirations and set them up on the customer card. To do this, go to the customer card and find the **Expiration Groups** tab. Here you can select the customer-specific expiration group.

### Customer-Specific Expiration Groups

Customer expiration groups can be specific to a single customer or standard ones that can be used for different customers.

First, create a new customer expiration group. To do this, select **New > Add Code > Add Description** from the menu.

Now, define which products belong to this customer expiration group. To do this, select **Related > Customer Expirations** from the menu.

In the opened table, create rows for the items or item categories. Select **Edit List > Type > Code** from the menu. If the item's shelf life for the customer is set on the item card, the value will immediately appear in the "Item Expiration Customer" column.

Next, you need to set either the "Expiration Time (%)" value or the "Expiration (Days)".

If the value in the "Item Expiration Customer" field on the item card is changed, you can recalculate the values as follows: **More Options > Actions > Recalculate Expirations**.

# How to use

## Sales Orders

Once the configurations are completed, adding batches to Sales Order lines is done as follows. Enter the items to be shipped with batches on the Sales Order lines. To add batches, do the following: From the **Lines menu, select: Line > Add Batches**.

## Assembly Orders

If items moving with a batch are part of a BOM (Bill of Materials), you can add batches to these items on the Assembly Order lines as follows: **Lines > Line > Add Batches**.

Note: Only FIFO and FEFO methods can be used for batch assignment on Assembly Orders.

## Item Journals

If you want to write off products with a Negative adjustment through the Item Journal, you can also add batches to the lines automatically. This is done as follows: From the menu, select **Line > Add Batches**.

Note: Only FIFO and FEFO methods can be used for batch assignment in Item Journals.
