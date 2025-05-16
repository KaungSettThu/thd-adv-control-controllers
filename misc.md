HighestFName1 <- ""
HigestSName1 <- ""
HighestTotalSales1 <- 0

HighestFName2 <- ""
HigestSName2 <- ""
HighestTotalSales2 <- 0

TeamTotal <- 0
FOR Member <- 1 TO LENGTH(StaffSales)
    EachMemberTotal <- 0
    FOR Sale <- 4 TO LENGHT(StaffSales[Member])
        EachMemberTotal <- EachMemberTotal + StaffSales[Member, Sale]
    NEXT Sale

    TeamTotal <- TeamTotal + EachMemberTotal

    IF EachMemberTotal > HighestTotalSales1
        THEN
            HighestTotalSales2 <- HighestTotalSales1
            HighestFName2 <- HighestFName1
            HigestSName2 <- HighestSName1

            HighestTotalSales1 <- EachMemberTotal
            HighestFName1 <- StaffSales[Member, 2]
            HigestSName1 <- StaffSales[Member, 3]
        ELSE
            IF EachMemberTotal > HighestTotalSales1
                THEN
                    HighestTotalSales2 <- EachMemberTotal
                    HighestFName2 <- StaffSales[Member, 2]
                    HigestSName2 <- StaffSales[Member, 3]
            ENDIF
    ENDIF

NEXT Member

ArrayName[RowIndex, ColIndex]

