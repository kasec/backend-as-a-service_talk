# Backend as a service talk

## Content

1. History
2. Cloud Providers / Cloud services
3. Differences between IaaS & PaaS
4. Checkpoint
5. Que es Backend
6. Quienes son frontend developers
7. BaaS
8. Supabase
9. Target
10. FAQs, datos personales QR con el link del sitio
11. Sources

> Antes del checkpoint cada tema asociarlo con una imagen representativa y en el checkpoint mostrar lo que se vio con base a las imagenes que mostradas.

Igual agregar fuentes para que el guest pueda acceder a mas informacion al final



# Bakend as a service

Me gustaria saber como enseñan en la escuela hoy en dia, dado que ahora todos se puede consumir como servicio.

-- No es como que me hayan enseñado mucho en la escuela GGG --

Pero en mi caso (7 años hace) el enfoque era aun crear tu propio servidor y exponerlo (lo cual hoy en dia me doy cuenta que es bastante inseguro)

Siempre he considerado que aprender como funcionan las cosas desde bajo nivel es algo que te ayuda a entender, comprender y abordar problemas de forma mas efectiva. Aunque esto te puede llevar al Learning Syndrome.
Aunque ese conocimiento sirve de mucho o quizas no ya que es un enfoque tan comun y cada vez menos.

-- creo que lo he conversado con un par de personas aqui en distintos eventos. --


# Getting started

Antes de continuar, lo ideal es estar todos en la misma sintonia.

Que es backend?
Quienes son los frontend developers?

**Backend**
En desarrollo web, los flujos de desarrollo se dividen en 2:
backend y frontend
[insertar-meme-backend]

Backend is basicamente lo que corre del lado del servidor
((parentesis))
Es dificil saber que donde esta el limite del backend, hoy en dia que son epocas de especializacion hay distintos roles.
- Infrastructura
- Devops
- DBA

TL;DR
Servicios que consume el frontend(UI)

---------

## Platform as a service / Software as a service / Backend as a service (Cloud Providers)

-- aqui me estoy metiendo en aguas que no conozco muy bien, pero al menos --

Al menos para software development, por que si, esto no solo incluye solo desarrollo web (hacer sitios web estaticos)

**((parentesis))**
Alguien me comento hace unas semanas que cual era el fin de los sitios web, ya nadie quiere uno y mucho menos algo escrito a mano cuando, existe alguien en la india (o aqui en mexico), que lo puede hacer por 500 pesos, o existen herramientas (CMS (Wordpress y demas)) donde lo haces en 30 mins o hoy en dia que lo puedes hacer con AI con un prompt entonces si, no hay forma de competir. Sin embargo desarrollo web no es solo eso.

((regresando))
Hoy en dia las plataformas que ofrecen servicios son bastante comunes. Donde puedes contratar casi cualquier servicio con un click o drag&drop

Las mas famosas y que abarcan casi todo (hablando de software development) son AWS, GCP, Azure
Las antes mencionadas son las mas famosas y donde puedes hacer casi todo sin salir de la plataforma o contratar otro servicio o hacerlo por tu cuenta (incluso si quieres hacerlo por tu cuenta puedes usar sus recursos)

Despues tenemos unos que son mas de nicho:

- Vercel -> agil frontend development (lambda functions, static site, buckets)
- Netlify -> agil frontend development (lambda functions, static site, buckets)
- Digital ocean -> VPS y servicios similar pa backeneros
- Fly.io -> VPS, docker containers y servicios similar pa backeneros

Al final el punto principal

Aun un nicho mas pequeño

Backend as a service:

- supabase
- planetscale
- upstash

----

## Supabase

Supabase is a backend-as-a-service platform built around the Postgres database, and is an Open Source alternative to Firebase. It can reduce time to market by providing a ready to use backend that includes a database with real time capabilities, authentication, object storage and edge functions. You can use Supabase as a service via their managed offerings or self-host it on your own server or on a cloud provider.


## Porque Supabase?

Yo elegi supabase por una sencilla razon, tiene un plan gratuito.

Aunque despues encontre cosas que me gustaron, eso no quita lo buena que es (no tengo punto de comparacion)

Plataforma tiene ciertos modulos gratuitos.

- Authentication gratis? validacion de correos?
- Postgres databases and an different sdk to easily consume it
- Direct postgres connection so you can manage the database on your own
- Layer entre auth y database RLS
- Including PostgreSQL's policy engine, for fine-grained access rules.

Modulos:

- Auth
- Database
- Storage
- Edge functions
- Realtime

## Never write an API again (supabase slogan)
We introspect your database and provide instant APIs. Focus on building your product, while Supabase handles the CRUD.

((parentesis))

## Self-Hosting
Host Supabase on your own infrastructure.

Como supabase es una herramienta open source te permite que puedas hostearla en tu propio servidor o cloud provider
https://supabase.com/docs/guides/self-hosting

## Supabase Auth

Tiene distintos enfoques:
- Server side
- Password based
- Email(Magic Link or OTP)
- Phone login
- Social Login
- Enterprise SSO
- Anonimous Sing ins
- mobile deep linking
- Identity linking
- Multi factor authentication

## RLS
https://supabase.com/docs/guides/database/postgres/row-level-security

[inserta imagen de una postgres poliza]

```postgres
create policy "Individuals can view their own todos."ç
    on todos for select
    using ( (select auth.uid()) = user_id );
```



## Target (para quien)
- Objectivo de la charla

## Glosario

**Database**
Sets de datos que categorizan/clasifican informacion, las mas famosas son Bases de datos relacionales, no relacionales.
Estan tambien las de grafos y bases de datos vectoriales estos dias ampliamente usadas por Modelos de machine learning