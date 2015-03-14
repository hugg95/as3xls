# Formulas #

  * Right now as3xls displays formulas in human readable form and evaluates them but does not yet support converting formulas in human readable form into weird Excel form (RPN with tokens represented by numbers if you're curious).
  * Excel has several hundred built in functions. So far I've only implemented the easy ones like SUM, AVERAGE, and so on.
  * Cell references can be kinda funky. I suspect there are bugs lurking here and there.

# Formatting #

  * Excel has a rich and varied formatting vocabulary, which as3xls largely ignores.

# Writing #

  * Support for writing notes, formatting, or formulas does not yet exist.
  * Currently as3xls saves spreadsheets in the format used by Excel 2 which supports only one sheet per document.