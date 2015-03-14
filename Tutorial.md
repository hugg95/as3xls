#Get up to speed the Quick-and-dirty way

## Reading ##

  1. You need to get the Excel file into a ByteArray of some sort, whether by hook, crook, or Embed.
  1. Now you need to load it up like so:

```
var xls:ExcelFile = new ExcelFile();
xls.loadFromByteArray(myByteArray);
```

  1. The sheets are stored in an ArrayCollection as Sheet objects. These hold a bunch of Cell objects each of which has a value property. This returns a Number, a String, or a Date object depending on the contents. You can play with them like so:

```
var sheet:Sheet = xls.sheets[0];

var value:String = sheet.getCell(0, 0).value;
```

Each sheet also has a values ArrayCollection suitable for a DataGrid's dataProvider. To display a sheet in a DataGrid you'd do this:

```
myDataGrid.dataPovider = sheet.values;
```

## Formulas ##

The result of evaluating a formula is available in the value property. To get the a string representation of the formula, like "SIN(5)" or "A5\*SUM(B1:B28)" you use the Formula object:

```
sheet.getCell(0, 0).formula.formula.
```

If a cell doesn't contain a formula the formula property will be null.

## Writing ##

First create a sheet and resize it. If you want to resize it after putting in values those values will not be deleted.

```
var sheet:Sheet = new Sheet();
sheet.resize(10, 10).
```

Now you can put in some values.

```
sheet.setCell(0, 0, "Today's date:");
sheet.setCell(0, 1, new Date());
```

Now put the sheet into an ExcelFile and save it.

```
var xls:ExcelFile = new ExcelFile();
xls.sheets.addItem(sheet);
var bytes:ByteArray = xls.saveToByteArray();
```

That ByteArray can be saved to disk and the resulting file will be loadable by any version of Excel.