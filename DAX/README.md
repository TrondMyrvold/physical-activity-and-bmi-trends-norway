**This README shows how the DAX measurements was created in Power BI.

*Highest percentage measurement

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


