# Cómo manejar las opciones "Accept current change" / "Accept incoming change" / "Accept both changes"

Cuando VS Code muestra botones como "Accept current change", "Accept incoming change" o "Accept both changes", significa que el archivo tiene un conflicto de fusión (merge conflict). Esto ocurre cuando Git no puede combinar automáticamente los cambios de dos ramas o commits porque se han modificado las mismas líneas.

## ¿Qué significa cada opción?
- **Accept current change**: Conserva la versión que ya existía en tu rama local (lo que está entre `<<<<<<<` y `=======`).
- **Accept incoming change**: Conserva la versión que llega desde la otra rama o commit (lo que está entre `=======` y `>>>>>>>`).
- **Accept both changes**: Inserta ambas versiones, una tras otra, para que puedas integrarlas manualmente si es necesario.

## Pasos recomendados
1. **Revisa las diferencias**: Lee con atención ambas secciones del conflicto para entender qué aporta cada una.
2. **Elige la opción correcta** según lo que necesites mantener:
   - Usa *Accept current change* si tu versión local es la correcta.
   - Usa *Accept incoming change* si la versión remota debe reemplazar la local.
   - Usa *Accept both changes* si necesitas combinar manualmente partes de las dos versiones.
3. **Ajusta el código**: Después de aceptar, revisa que el resultado final tenga sentido. Puedes editar el archivo para limpiar duplicados o fusionar lógicas.
4. **Prueba y verifica**: Ejecuta las pruebas o revisa la funcionalidad relacionada para asegurarte de que el conflicto se resolvió correctamente.
5. **Marca el conflicto como resuelto**: Guarda el archivo, haz `git add` y luego un `git commit` (o continúa con `git merge --continue` si estabas en un merge).

## Consejos adicionales
- Usa la vista de *Source Control* en VS Code para navegar entre archivos con conflictos.
- Si te equivocas, siempre puedes deshacer los cambios con `git checkout -- <archivo>` y volver a intentarlo.
- Mantén una comunicación clara con tu equipo para entender qué cambios deben prevalecer cuando haya dudas.

