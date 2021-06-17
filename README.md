# ReutilizableCod

### Establecer zona horaria PHP
```
date_default_timezone_set('America/Bogota');
$hoy = date("Y-m-d H:i:s");    // 2001-03-10 17:16:18 (el formato DATETIME de MySQL)
```

### No deja escribir letras al input
```
function soloLetras(e) {
    key = e.keyCode || e.which;
    tecla = String.fromCharCode(key).toLowerCase();
    letras = " áéíóúabcdefghijklmnñopqrstuvwxyz";
    especiales = [8, 37, 39, 46];

    tecla_especial = false
    for(var i in especiales) {
      if(key == especiales[i]) {
          tecla_especial = true;
          break;
      }
    }

    if(letras.indexOf(tecla) == -1 && !tecla_especial)
      return false;
}

<--- onkeypress="return soloLetras(event)" --->

```

### No deja escribir numeros input

```
function validaNumericos(event) {
    if (event.charCode >= 48 && event.charCode <= 57) {
        return true;
    }
    return false;
}

<--- onkeypress="return validaNumericos(event)" --->
```
### Mayusculas automaticas
```
<--- onkeyup="this.value = this.value.toUpperCase();" --->
```

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
