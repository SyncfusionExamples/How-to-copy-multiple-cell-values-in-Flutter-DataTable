# How to copy multiple cell values in Flutter DataTable (SfDataGrid)?.

In this article, we will show you how to copy multiple cell values in [Flutter DataTable](https://www.syncfusion.com/flutter-widgets/flutter-datagrid).

Initialize the [SfDataGrid](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid-class.html) with the necessary properties. By using [SelectionArea](https://api.flutter.dev/flutter/material/SelectionArea-class.html), you can copy multiple cell values. Setting SelectionArea as the parent of SfDataGrid allows you to copy the entire cell content to the clipboard by dragging. To achieve this, enable [SfDataGrid.shrinkWrapRows](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid/shrinkWrapRows.html) to prevent row reuse during scrolling. However, keep in mind that enabling shrinkWrapRows constructs all rows during the initial load.

```dart
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Syncfusion Flutter DataGrid'),
      ),
      body: SelectionArea(
        child: SfDataGrid(
          source: employeeDataSource,
          shrinkWrapRows: true,
          columnWidthMode: ColumnWidthMode.fill,
          columns: <GridColumn>[
            GridColumn(
                columnName: 'id',
                label: Container(
                    padding: const EdgeInsets.all(16.0),
                    alignment: Alignment.center,
                    child: const Text(
                      'ID',
                    ))),
            GridColumn(
                columnName: 'name',
                label: Container(
                    padding: const EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: const Text('Name'))),
            GridColumn(
                columnName: 'designation',
                label: Container(
                    padding: const EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: const Text(
                      'Designation',
                      overflow: TextOverflow.ellipsis,
                    ))),
            GridColumn(
                columnName: 'salary',
                label: Container(
                    padding: const EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: const Text('Salary'))),
          ],
        ),
      ),
    );
  }
```

You can download this example on [GitHub](https://github.com/SyncfusionExamples/How-to-copy-multiple-cell-values-in-Flutter-DataTable).