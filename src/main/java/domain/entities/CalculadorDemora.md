```java
package domain.entities;

public class CalculadorDemora {
public Float calcularDemoraEntre2Ubicaciones(Ubicacion origen, Ubicacion destino){
return 0;
}

    public Float calcularDemora(Ubicacion ... paradas){
        Float demoraTotal = 0;
        for (int i = 0; i < paradas.length - 1; i++) {
            demoraTotal += calcularDemoraEntre2Ubicaciones(paradas[i], paradas[i + 1]);
        }
        return demoraTotal;
    }
}
```