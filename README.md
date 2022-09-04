# pdf_work-

If someone want to convert lots of *pdf Tables into csv* then copy this code: 



#getting File Location

for i in glob('C:/Users/Utkarsh Tripathi/Downloads/com/All_files/*.pdf'):
    print(i)
    name = input("For which name U want to save Your Excle File ??.... ")

    
    
    
    #Getting total pages in pdf 
    file = open(f'{i}', 'rb')
    readpdf = PyPDF2.PdfFileReader(file)
    totalpages = readpdf.numPages
    print(totalpages)
    
    
    
    
    
    #converting into Excel
    x = 1
    while x <= totalpages:
        tabula.convert_into(f"{name}.pdf", f"{name}  {x}.csv", output_format="csv", pages=f"{x}")
        x = x + 1
