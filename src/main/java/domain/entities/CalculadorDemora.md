```java
package domain.entities;

public class CalculadorDemora {
    Float tiempoParaTransladarseSobreUnidadDeDistancia;

    public Float calcularDemora(Viaje unViaje, Ubicacion origen, Ubicacion ... parada){
        Float demoraTotal = calcularDemoraEntre2Ubicaciones(unViaje, origen, paradas[0]);
        for (int i = 0; i < paradas.length - 1; i++) {
            demoraTotal += calcularDemoraEntre2Ubicaciones(unViaje, paradas[i], paradas[i + 1]);
        }
        return demoraTotal;
    }

    public Float calcularDemoraEntre2Ubicaciones(Viaje unViaje, Ubicacion origen, Ubicacion destino){
        return this.tiempoParaTransladarseSobreUnidadDeDistancia * this.calcularDistancia(unViaje, origen, destino);
    }

    public float calcularDistancia(Viaje unViaje, Ubicacion origen, Ubicacion destino){
        return unViaje.calcularDistanci(origen, destino);
    }
}
```