# ReutilizableCod

### Fechas automaticas en input date

```
value="<?php echo $fi = isset($_POST['FechaInicio']) ? $_POST['FechaInicio'] : date('Y-m-d'); ?>" 
```

### Rellenar listas con JS y PHP

```
function RellenarListas() {
    ListadoClientes = '<?php echo $ListadoCliente ?>';
    $("#Cliente").append(ListadoClientes);
    $('#Cliente option[value="<?php echo $ActCliente; ?>"]').attr('selected', true);

    ListadoCampana = '<?php echo $ListadoCampana ?>';
    $("#Campana").append(ListadoCampana);
    $('#Campana option[value="<?php echo $ActCampana; ?>"]').attr('selected', true);

    ListadoArea = '<?php echo $ListadoArea ?>';
    $("#Area").append(ListadoArea);
    $('#Area option[value="<?php echo $ActArea; ?>"]').attr('selected', true);

    ListadoPermiso = '<?php echo $ListadoPermiso ?>';
    $("#TipoPermiso").append(ListadoPermiso);
    $('#TipoPermiso option[value="<?php echo $ActPermiso; ?>"]').attr('selected', true);

    ListadoCargo = '<?php echo $ListadoCargo ?>';
    $("#Cargo").append(ListadoCargo);
    $('#Cargo option[value="<?php echo $ActCargo; ?>"]').attr('selected', true);

    ListadoGrupo = '<?php echo $ListadoGrupo ?>';
    $("#Grupo").append(ListadoGrupo);
    $('#Grupo option[value="<?php echo $ActGrupo; ?>"]').attr('selected', true);

    ListadoSubGrupo = '<?php echo $ListadoSubGrupo; ?>';
    $("#SubGrupo").append(ListadoSubGrupo);
    $('#SubGrupo option[value="<?php echo $ActSubgrupo; ?>"]').attr('selected', true);

    ListadoNivel = '<?php echo $ListadoNivel ?>';
    $("#Nivel").append(ListadoNivel);
    $('#Nivel option[value="<?php echo $ActNivel; ?>"]').attr('selected', true);
}
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
