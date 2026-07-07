// This README shows how the DAX measurements was created in Power BI.

------------------------------------------------------------------------------
// Highest percentage measurement

Highest percentage = 
VAR LatestYear =
    MAX('06181'[Year])

VAR TopRow =
    TOPN(
        1,
        FILTER(
            ALLSELECTED('06181'),
          '06181'[Year] = LatestYear &&
            '06181'[Age] <> "Age, total"
        ),
        '06181'[Percent],
        DESC
    )

RETURN
MAXX(TopRow, '06181'[Age]) &
" (" &
FORMAT(MAXX(TopRow, '06181'[Percent]), "0") &
"%)"

------------------------------------------------------------------------------

// Highest value measurement

Highest Value = 
VAR LatestYear = [Latest Year]
VAR SummaryTable =
    FILTER(
        ALLSELECTED('06181'),
        '06181'[Year] = LatestYear &&
        '06181'[Age] <> "Age, total"
    )
RETURN
    MAXX(SummaryTable, '06181'[Percent])

------------------------------------------------------------------------------

// Lowest percentage measurement

Lowest percentage = 
VAR LatestYear =
    MAX('06181'[Year])

VAR BottomRow =
    TOPN(
        1,
        FILTER(
            ALLSELECTED('06181'),
            '06181'[Year] = LatestYear &&
            '06181'[Age] <> "Age, total"
        ),
        '06181'[Percent],
        ASC
    )

RETURN
MAXX(BottomRow, '06181'[Age]) &
" (" &
FORMAT(MAXX(BottomRow, '06181'[Percent]), "0") &
"%)"

------------------------------------------------------------------------------

// Overall change measurement

Overall change = 
VAR LatestYear =
    MAX('06181'[Year])

VAR FirstValue =
    CALCULATE(
        AVERAGE('06181'[Percent]),
        FILTER(
            ALLSELECTED('06181'),
            '06181'[Year] = 1998 &&
            '06181'[Age] = "Age, total"
        )
    )

VAR LatestValue =
    CALCULATE(
        AVERAGE('06181'[Percent]),
        FILTER(
            ALLSELECTED('06181'),
            '06181'[Year] = LatestYear &&
            '06181'[Age] = "Age, total"
        )
    )

VAR Difference =
    LatestValue - FirstValue

RETURN
IF(
    Difference >= 0,
    "+" & FORMAT(Difference, "0") & " percentage points ",
    FORMAT(Difference, "0") & " percentage points "
)

------------------------------------------------------------------------------

//Selected indicator measurement

Selected indicator = 
SELECTEDVALUE('06181'[Lifestyle Habit], "Select an exercise habit")

------------------------------------------------------------------------------
