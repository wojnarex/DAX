https://www.youtube.com/watch?v=fLbTFFEEzRk

-- I option
Chart Title - SWITCH = 
VAR TitleStart = "Sales for "
VAR TitleVar = 
SWITCH(
    TRUE(),
    SELECTEDVALUE(dimDate[Year])=2020,"Current Year",
    SELECTEDVALUE(dimDate[Year])&""
)
RETURN
TitleStart&TitleVar

-- II option
Chart Title - Subcategories Selection = 
"Sales for "&
CONCATENATEX(
    VALUES(dimProduct[ProductSubcategoryName]),
    dimProduct[ProductSubcategoryName],
    ", ",
    dimProduct[ProductSubcategoryName],
    ASC
) 

-- III option
Chart Title - Subcategory Selection = "Sales for Subcategory "&SELECTEDVALUE(dimProduct[ProductSubcategoryName])

-- IV option
Chart Title - Subcategories & Year = 
COMBINEVALUES(
    ", ",
    [Chart Title - Year Selection],
        [Chart Title - Subcategories Selection]
)
