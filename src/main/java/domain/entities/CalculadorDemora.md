```java
package domain.entities;

public class CalculadorDemora {
    Float tiempoParaTransladarseSobreMetro;

    public Float calcularDemora(Viaje unViaje, Ubicacion origen, Ubicacion ... parada) {
        Float demoraTotal = calcularDemoraEntre2Ubicaciones(unViaje, origen, paradas[0]);
        Integer cantidadParadas = 0;
        while (cantidadParadas < paradas.length - 1) {
            demoraTotal += calcularDemoraEntre2Ubicaciones(unViaje, paradas[cantidadParadas], paradas[cantidadParadas + 1]);
            cantidadParadas++;
        }
        if (unViaje.getTiempoDetenido() == 0) { // Lo dejamos para ganar expresividad, podría no estar ya que en el return se contempla este caso
            return demoraTotal;
        }
        return demoraTotal + (unViaje.getTiempoDetenido() * cantidadParadas);
    }
    }

    public Float calcularDemoraEntre2Ubicaciones(Viaje unViaje, Ubicacion origen, Ubicacion destino){
        return this.tiempoParaTransladarseSobreMetro * this.calcularDistancia(unViaje, origen, destino);
    }

    public float calcularDistancia(Viaje unViaje, Ubicacion origen, Ubicacion destino){
        return unViaje.calcularDistancia(origen, destino);
    }
```