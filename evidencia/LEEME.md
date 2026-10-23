# Evidencia de funcionamiento — ArcadeShelf API

Repositorio: https://github.com/manuelpianeta6393-maker/Web_API_games_fixed

Ejecución: `python -m uvicorn main:app --reload` y pruebas desde Swagger (`http://127.0.0.1:8000/docs`), partiendo de una base de datos vacía.

| Archivo | Prueba | Resultado esperado |
|---|---|---|
| 00_swagger.png | Swagger con los 4 endpoints | — |
| P01_crear_juego_201.png | POST /games (Hollow Knight, stock 5) | 201, `id: 1`, `active: true` |
| P01b_crear_segundo_juego_201.png | POST /games (Hades, stock 3) | 201, `id: 2` |
| P02_stock_0_422.png | POST /games con `stock: 0` | 422 |
| P03_listar_juegos_200.png | GET /games | 200, lista con 2 juegos |
| P04_consultar_id_1_200.png | GET /games/1 | 200 |
| P05_id_999_404.png | GET /games/999 | 404, `Game not found` |
| P06_eliminar_id_1_200.png | DELETE /games/1 | 200, `Game deleted` |
| P06b_consultar_id_1_tras_eliminar_404.png | GET /games/1 después de eliminar | 404 |
| P07_listar_tras_reiniciar_200.png | GET /games después de reiniciar Uvicorn | 200, solo queda Hades (persistencia) |
