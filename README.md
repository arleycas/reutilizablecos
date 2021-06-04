# ReutilizableCod

### Fechas automaticas en input date

```
value="<?php echo $fi = isset($_POST['FechaInicio']) ? $_POST['FechaInicio'] : date('Y-m-d'); ?>" 
```
## Materialize
### Evento onclose Modales

```
$('.modal').modal({
    dismissible: true, // Modal can be dismissed by clicking outside of the modal
    onCloseEnd: function() { // Callback for Modal close
        alert('Closed');
    }
});

```

## Datatable

### Limpiar input search y redibujar los datos de la tabla con codigo

```
$('#id_de_tabla').DataTable().search('').draw();
```
