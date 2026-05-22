
# U12 Post 2 - Validacion Arquitectonica

## Resumen
Repositorio basado en el Post 1 con reglas ArchUnit, ADRs y pipeline de CI para
validar la arquitectura en cada push.

## Validacion Arquitectonica (ArchUnit)
- Regla 1: el dominio no depende de infraestructura ni adaptadores.
- Regla 2: los controladores solo acceden a la facade.
- Regla 3: los puertos del dominio son interfaces.
- Regla 4: los procesadores implementan `ProcesadorPedido`.
- Regla 5: la infraestructura no accede a adaptadores REST.

Archivo de reglas: src/test/java/com/empresa/pedidos/ReglasArquitectura.java

## ADRs
- [docs/adr/ADR-001.md](docs/adr/ADR-001.md)
- [docs/adr/ADR-002.md](docs/adr/ADR-002.md)
- [docs/adr/ADR-003.md](docs/adr/ADR-003.md)

## Pipeline CI
- Workflow: .github/workflows/arquitectura.yml
- Ejecuta `mvn test -Dtest=ReglasArquitectura` y `mvn verify`.

## Capturas
<img width="1159" height="318" alt="image" src="https://github.com/user-attachments/assets/92344ad4-7942-4875-b09c-4b42a804dd99" />

<img width="1169" height="304" alt="image" src="https://github.com/user-attachments/assets/5d95a5c2-3fa8-41b4-bc1e-ad09181b1680" />

<img width="737" height="632" alt="image" src="https://github.com/user-attachments/assets/5c1764a1-4922-4e7d-a798-e7b26252f579" />



## Ejecucion local
1. Solo reglas: `mvn test -Dtest=ReglasArquitectura`.
2. Suite completa: `mvn verify`.
