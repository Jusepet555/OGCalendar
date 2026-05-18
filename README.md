# OG Calendar Cloud

OG Calendar Cloud és una eina web de calendari i registre de treball per a hort o jardí.

La versió actual estable amb backend és:

**OG Calendar Cloud v16**

## Estat del projecte

Aquesta versió funciona amb:

- registre d’usuari amb email i contrasenya;
- guardat automàtic al núvol amb Supabase;
- càrrega automàtica de les dades del núvol en iniciar sessió;
- dades separades per usuari;
- varietats;
- plantes individuals dins de cada varietat;
- registres associats a tota una varietat o a una planta concreta;
- calendari;
- mode fosc;
- idiomes;
- exportació normal;
- exportació lleugera sense fotos;
- opció per esborrar les dades del núvol de l’usuari actual.

## Avís de responsabilitat

L’edat mínima per utilitzar aquesta eina és de 21 anys.

Aquesta pàgina no promou l’ús de cap tipus de substància. És una eina de registre i organització del calendari de treball a l’hort o al jardí.

## Ús bàsic

1. Obrir l’enllaç de l’app.
2. Crear un compte amb email i contrasenya.
3. Entrar amb l’usuari.
4. Crear varietats.
5. Afegir plantes si cal.
6. Afegir registres de treball.
7. L’app guarda els canvis automàticament al núvol.

## Backend

El backend utilitzat és Supabase.

Taula principal:

```sql
public.og_calendar_data
```

La taula guarda les dades de cada usuari separades per `user_id`.

La seguretat es controla amb RLS:

```text
auth.uid() = user_id
```

Això fa que cada usuari només pugui llegir, crear, modificar o esborrar les seves pròpies dades.

## Versions importants

### OG Calendar v32 local

Versió estable sense backend.

Serveix com a còpia local funcional i independent de Supabase.

### OG Calendar Cloud v16

Primera base bona amb backend.

Inclou login, guardat al núvol, càrrega automàtica, record de sessió, tancament de sessió i dades separades per usuari.

## Procediment de treball

No modificar directament la versió bona.

A partir d’ara:

```text
Cloud v16 = base bona
Cloud v17 = proper canvi petit
Cloud v18 = següent canvi petit
```

Cada canvi s’hauria de provar abans de substituir la versió publicada.

## Notes

Encara que l’app ja guarda dades al núvol, les fotos continuen sent un punt delicat perquè poden ocupar molt espai. Més endavant es pot valorar guardar les fotos a Supabase Storage en lloc de dins del JSON de dades.
