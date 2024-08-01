Sub CreateChart()
    Dim ws As Worksheet
    Dim chartObj As ChartObject

    ' Tham chiếu đến bảng tính hiện tại
    Set ws = ThisWorkbook.Sheets("Sheet1")

    ' Thêm dữ liệu mẫu
    ws.Range("A1:B4").Value = Array(Array("Month", "Sales"), Array("Jan", 100), Array("Feb", 120), Array("Mar", 140))

    ' Tạo một đối tượng biểu đồ
    Set chartObj = ws.ChartObjects.Add(Left:=100, Width:=375, Top:=50, Height:=225)

    ' Thiết lập nguồn dữ liệu cho biểu đồ
    With chartObj.Chart
        .SetSourceData Source:=ws.Range("A1:B4")
        .ChartType = xlColumnClustered
        .HasTitle = True
        .ChartTitle.Text = "Monthly Sales"
    End With
End Sub

