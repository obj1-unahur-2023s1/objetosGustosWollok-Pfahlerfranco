# Gustos

Se nos pide armar un programa que ayude a entender qué cosas le gustan a distintas personas.


## Objetos y personas

Tener en cuenta a estas personas:
- _Rosa_: le gustan las cosas que pesan 2 kilos (o sea 2000 gramos) o menos.
- _Estefanía_: le gustan las cosas de colores fuertes.
- _Luisa_: le gustan las cosas que sean de un material que brilla.
- _Juan_: le gustan las cosas que, o bien son de un color que no es fuerte, o bien pesan entre 1200 y 1800 gramos.

Como **colores** contemplar (al menos) rojo, verde, celeste y pardo. 
De estos, los dos primeros son fuertes, los otros no.

Como **materiales** tenemos: el cobre y el vidrio que brillan; el lino, la madera y el cuero que no.

Finalmente, considerar (al menos) estos objetos:
  - una _remera_ roja de lino, pesa 800 gramos.
  - una _pelota_ parda de cuero, pesa 1300 gramos.
  - una _biblioteca_ verde de madera, pesa 8000 gramos.
  - un _muñeco_ celeste de vidrio, de peso variable.
  - una _placa_ de cobre, de peso y color variables.

RESOLUCIÓN:
/* colores */
object rojo { method esFuerte() { return true } }
object verde { method esFuerte() { return true } }  // completar
object celeste { method esFuerte() { return false } }  // completar
object parda { method esFuerte() { return false } }  // completar

/* materiales */
object lino { method brilla() { return false } }
object vidrio { method brilla() { return true } }
object cobre { method brilla() { return true } }
object madera { method brilla() { return false } }
object cuero { method brilla() { return false } }
// agregar: cobre, madera, cuero

/* objetos */
object remera {
	method color() { return rojo }
	method material() { return lino }
	method peso() { return 800 }
}

object pelota {
	method color() { return parda }  // completar
	method material() { return cuero }  // completar
	method peso() { return 1300 }  // completar
}

object munieco {
	var peso 
	
	method color() { return celeste }
	method material() { return vidrio }
	method peso() { return peso }
	// usar siempre setPeso y setColor para setear los nuevos peso y color, respectivamente.
	method setPeso(pesoNuevo) { peso = pesoNuevo }
}
object placa {
	var color
  var peso
	
	method color() { return color }
	method material() { return cobre }
	method peso() { return peso }
	// usar siempre setPeso y setColor para setear los nuevos peso y color, respectivamente.
	method setColor(colorNuevo) { color = colorNuevo   }
  method setPeso(pesoNuevo) { peso = pesoNuevo }
}
object biblioteca {
	method color() { return verde }  // completar
	method material() { return madera }  // completar
	method peso() { return 8000 }  // completar
// agregar biblioteca y placa
}

object estefania {
	method leGusta(objeto) { return objeto.color().esFuerte() }
}

object rosa {
	method leGusta(objeto) { return
  objeto.peso() <= 2000}  // completar
}
object luisa {
  method leGusta(objeto){ return objeto.material().brilla()}
}

object juan {
  method leGusta(objeto){ return not objeto.color().esFuerte() or  (  objeto.peso() >= 1200 and objeto.peso() <= 2000  )
  }
}

// agregar luisa y juan


## Bolichito

Agregar al modelo un bolichito, que vende dos objetos: uno está en la vidriera, otro está en el mostrador.
Estos objetos van cambiando con el tiempo.

Se esperar que el objeto que representa al bolichito responda a estos mensajes:
- `esBrillante()`: indica si los dos objetos que tiene (el de mostrador y el de vidriera) son de un material que brilla.

- `esMonocromatico()`: indica si los dos objetos que tiene son del mismo color. <br> 
  Esto se daría si tiene p.ej. la remera en mostrador y la placa en vidriera, 
  y la placa se configura como de color rojo y peso 2400 gramos.
  
- `estaDesequilibrado()`: indica si el objeto en el mostrador pesa más que el de la vidriera. <br> 
  P.ej. si el bolichito tiene la biblioteca en el mostrador y la remera en la vidriera, está desequilibrado.
  
- `tieneAlgoDeColor(color)`: indica si alguno de los dos objetos que tiene el boliche es del color indicado. <br>
  P.ej. si el bolichito tiene la biblioteca en la vidriera y la remera en el mostrador, 
  entonces tiene algo de color rojo y tiene algo de color verde, pero no tiene nada de color pardo.
  
- `puedeMejorar()`: indica si el bolichito puede mejorar en uno de los siguientes aspectos: o bien está desequilibrado (falta de equilibrio), o bien es monocromático (falta de alegría).
  
- `puedeOfrecerleAlgoA(persona)`: indica si alguno de los dos objetos que tiene en venta el boliche le gustan a la persona. <br>
  P.ej. si el bolichito tiene la remera en la vidriera y la pelota en el mostrador,
  entonces puede ofrecerle algo a Estefanía (la remera) y a Juan (la pelota) 
  pero no a Luisa (porque no le gustan ni la remera ni la pelota).
  
  
## Más cosas

Agregar al modelo estos objetos:

- un _arito_ celeste de cobre, que pesa 180 gramos.
- un _banquito_ de madera que pesa 1700 gramos. 
  Al principio es naranja, pero puede cambiar de color. 
  El naranja es un color fuerte.
- una _cajita_ roja de cobre, que tiene un objeto adentro. 
  Este objeto puede ser cualquiera de los definidos previamente, y puede cambiar.
  El peso de la cajita es de 400 gramos más el peso de lo que tiene adentro.
    
  
