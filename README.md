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
const inputSoloNum = (arrInputs = []) => {
  arrInputs.forEach((element) => {
    element.addEventListener('keypress', (e) => {
      if (e.charCode >= 48 && e.charCode <= 57) {
        return true;
      }
      e.preventDefault();
      return false;
    });
  });
};

// Se le pasan todos los inputs que sean númericos
inputSoloNum(document.querySelectorAll('.inp-solo-num'));

```

### No deja escribir espacios al input
```
function validarEspacio(e) {

    if((e.code == 'Space') || (e.key == " ")) {
        e.preventDefault();
        return false; 
    }       
    return true;     
}

<--- onkeypress="validarEspacio(event)" --->
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
}
```

### Edad automática con fecha

```
//Función para calcular edad automáticamente
$('#DatosBasicosUsuarioFechaNacimiento').change(function(){
    const Hoy = new Date();
    const FechaNacimiento = new Date($(this).val() + 'T23:59:59');

    const DiaNa = FechaNacimiento.getDate();
    const MesNa = (FechaNacimiento.getMonth() + 1);
    const AnoNa = FechaNacimiento.getFullYear();

    const DiaHoy = Hoy.getDate();
    const MesHoy = (Hoy.getMonth() + 1);
    const AnoHoy = Hoy.getFullYear();
    let UnidadMedida = '';

    //Calculo de años
    let EdadAnos = AnoHoy - AnoNa;
    if(MesHoy < MesNa) {
        EdadAnos--;
    }
    if((MesHoy == MesNa) && (DiaHoy < DiaNa)) {
        EdadAnos--;
    }

    //Calculo de meses
    let EdadMeses = 0;

    if((MesHoy > MesNa) && (DiaNa > DiaHoy))
        EdadMeses = MesHoy - MesNa - 1;
    else if (MesHoy > MesNa)
        EdadMeses = MesHoy - MesNa
    if (MesHoy < MesNa && DiaNa < DiaHoy)
        EdadMeses = 12 - (MesNa - MesHoy);
    else if (MesHoy < MesNa)
        EdadMeses = 12 - (MesNa - MesHoy + 1);
    if (MesHoy == MesNa && DiaNa > DiaHoy)
        EdadMeses = 11;

    //Calculo de días
    let EdadDias = 0;

    if (DiaHoy > DiaNa)
    EdadDias = DiaHoy - DiaNa;
    if (DiaHoy < DiaNa) {
        UltimoDiaMes = new Date(AnoHoy, MesHoy - 1, 0);
        EdadDias = UltimoDiaMes.getDate() - (DiaNa - DiaHoy);
    }

    //Establece la edad (en el input) y el tipo de unidad de medida para la edad
    if(EdadAnos > 0) {
        UnidadMedida = 'Anos';
        $('#DatosBasicosUsuarioEdad').val(EdadAnos);
        $('#DatosBasicosUsuarioAnos').prop('checked', true);
    }else if((EdadAnos < 1) && (EdadMeses > 0)) {
        UnidadMedida = 'Meses';
        $('#DatosBasicosUsuarioEdad').val(EdadMeses);
        $('#DatosBasicosUsuarioMeses').prop('checked', true);
    }else if((EdadAnos < 1) && (EdadMeses < 1) && (EdadDias >= 0)) {
        UnidadMedida = 'Dias';
        $('#DatosBasicosUsuarioEdad').val(EdadDias);
        $('#DatosBasicosUsuarioDias').prop('checked', true);
    }

    M.updateTextFields(); //Reactiva inputs
});
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
