Estoy en un ASUS ROG Zephyrus G14 con dual boot Ubuntu 24.04 + Windows 11.

Quiero crear en Windows un usuario nuevo llamado **Steph**, separado de mi usuario **Felipe**.

Objetivo:
- Felipe mantiene su perfil, archivos y contraseña/PIN.
- Steph tendrá su propio perfil desde cero.
- Steph debe ser **usuario estándar, NO administrador**.
- Quiero que Steph tenga su propio `C:\Users\Steph`.
- Felipe tiene que seguir protegido por contraseña/PIN para que Steph no pueda entrar a mi sesión.
- Quiero hacerlo lo máximo posible desde Ubuntu/Linux.

Ya identificamos las particiones:

```text
/dev/nvme0n1p1 = EFI
/dev/nvme0n1p2 = Microsoft Reserved 16 MB
/dev/nvme0n1p3 = Windows, NTFS, 318.8 GB
/dev/nvme0n1p4 = otra partición NTFS
/dev/nvme0n1p5 = Linux /datos
/dev/nvme0n1p6 = Ubuntu /
```

La partición principal de Windows es:

```bash
/dev/nvme0n1p3
```

Ya ejecuté desde Ubuntu un bloque que montó Windows y creó estos archivos:

```text
C:\Users\Public\StephSetup\crear-steph.ps1
C:\Users\Public\StephSetup\EJECUTAR-COMO-ADMINISTRADOR.bat
```

El script PowerShell está diseñado para:
- Crear el usuario local `Steph`
- Pedir una contraseña para Steph
- Agregarla al grupo `Users`
- Quitarla de `Administrators`
- Dejarla como usuario estándar

El siguiente paso era:

1. Reiniciar desde Ubuntu hacia Windows.
2. Entrar a mi cuenta Felipe.
3. Ir a:

```text
C:\Users\Public\StephSetup\
```

4. Ejecutar como administrador:

```text
EJECUTAR-COMO-ADMINISTRADOR.bat
```

5. Elegir la contraseña para Steph.
6. Verificar que Steph aparezca en la pantalla de inicio de sesión.
7. Entrar una vez en Steph para que Windows cree:

```text
C:\Users\Steph
```

Después quiero que me ayudes a comprobar que:
- Steph NO sea administradora.
- Felipe siga protegido.
- Steph no pueda acceder normalmente a mis archivos personales.
- Cada uno tenga Escritorio, Documentos, Descargas, navegador y configuraciones separados.
- No modifiquemos el SAM de Windows manualmente ni usemos trucos como `utilman.exe`.

Continúa exactamente desde ese punto y dame comandos concretos, preferiblemente bloques completos para copiar y pegar.

# Lirio
