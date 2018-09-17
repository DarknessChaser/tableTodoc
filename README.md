# tableTodoc
一个简单的table元素导出到doc的库，不会保存样式，超级原始。

是huanz@GitHub的table到出库个人修改版，源地址见[https://github.com/huanz/tableExport](https://github.com/huanz/tableExport)/

导入`tableExport.js`文件即可使用

调用方式为
```
    tableExport('testTable', 'test', 'doc');
    // 参数分别为 要导出table的id，文件名，文档类型（有且仅有doc一个选项）
```

如果需要导出多个table可以参考例子中，把多个table合成变成一个table，插入到body后再删除，因为库里面使用getdocumentbyid方法获取table元素不插入找不到。
```
    var myTable = document.createElement("table");
    var tableHtml = ''
    var allTable = document.querySelectorAll('table')
    for (var i = 0; i < allTable.length; i++) {
        tableHtml += allTable[i].querySelector('tbody').innerHTML;
    }
    myTable.innerHTML = tableHtml
    myTable.setAttribute('id','testTable')
    document.querySelector("body").appendChild(myTable)
    tableExport('testTable', 'test', 'docx');
    document.querySelector("body").removeChild(myTable)
```
