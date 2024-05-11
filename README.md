# Base de Datos de la Champions League MongoDB

Este repositorio contiene los scripts de creación de colecciones y documentos de ejemplo para una base de datos MongoDB destinada a gestionar información relacionada con la Champions League.

# Estudiantes

- Oliver Sebastian Borda Mahecha
- David Andrés Rincón López

# Descripción de la Actividad

Esta actividad forma parte de un curso introductorio sobre bases de datos NoSQL utilizando MongoDB. Los participantes tienen la tarea de diseñar una base de datos MongoDB que permita gestionar información relacionada con un torneo deportivo, en este caso, la Champions League. La base de datos debe incluir colecciones para almacenar datos sobre deportistas, equipos, entrenadores, árbitros, encuentros deportivos, resultados y la tabla de posiciones. Los participantes deben crear scripts de creación de colecciones y proporcionar ejemplos de documentos JSON para cada colección, siguiendo los lineamientos y requisitos establecidos en el curso.

# Estructura de la Base de Datos

La base de datos consta de las siguientes colecciones:

1. **Deportistas**
2. **Equipos**
3. **Entrenadores**
4. **Árbitros**
5. **Encuentros Deportivos**
6. **Resultados**
7. **Tabla de Posiciones**

# Creación de las Colecciones

1. **Deportistas:**
db.createCollection("Deportistas")

2. **Equipos:**
db.createCollection("Equipos")

3. **Entrenadores:**
db.createCollection("Entrenadores")

4. **Árbitros:**
db.createCollection("Árbitros")

5. **Encuentros Deportivos:**
db.createCollection("EncuentrosDeportivos")

6. **Resultados:**
db.createCollection("Resultados")

7. **Tabla de Posiciones:**
db.createCollection("TablaDePosiciones")

# Documentos de Ejemplo

## Deportistas

db.Deportistas.insert([
  {
    "nombre": "string",
    "edad": "int",
    "nacionalidad": "string",
    "equipo": {
      "type": "ObjectId",
      "ref": "Equipos"
    }
  },
  {
    "nombre": "Lionel Messi",
    "edad": 34,
    "nacionalidad": "Argentina",
    "equipo": "ID_EQUIPO"
  },
  {
    "nombre": "Cristiano Ronaldo",
    "edad": 36,
    "nacionalidad": "Portugal",
    "equipo": "ID_EQUIPO"
  },
  {
    "nombre": "Neymar Jr",
    "edad": 29,
    "nacionalidad": "Brasil",
    "equipo": "ID_EQUIPO"
  },
  {
    "nombre": "Kevin De Bruyne",
    "edad": 30,
    "nacionalidad": "Bélgica",
    "equipo": "ID_EQUIPO"
  },
  {
    "nombre": "Robert Lewandowski",
    "edad": 33,
    "nacionalidad": "Polonia",
    "equipo": "ID_EQUIPO"
  }
]);

## EncuentrosDeportivos

db.EncuentrosDeportivos.insert([
  {
    "fecha": "date",
    "lugar": "string",
    "equipo_local": {
      "type": "ObjectId",
      "ref": "Equipos"
    },
    "equipo_visitante": {
      "type": "ObjectId",
      "ref": "Equipos"
    },
    "arbitro": {
      "type": "ObjectId",
      "ref": "Árbitros"
    }
  },
  {
    "fecha": "2024-05-15",
    "lugar": "Estadio Santiago Bernabéu",
    "equipo_local": "ID_EQUIPO",
    "equipo_visitante": "ID_EQUIPO",
    "arbitro": "ID_ARBITRO"
  },
  {
    "fecha": "2024-05-16",
    "lugar": "Estadio Camp Nou",
    "equipo_local": "ID_EQUIPO",
    "equipo_visitante": "ID_EQUIPO",
    "arbitro": "ID_ARBITRO"
  },
  {
    "fecha": "2024-05-17",
    "lugar": "Allianz Arena",
    "equipo_local": "ID_EQUIPO",
    "equipo_visitante": "ID_EQUIPO",
    "arbitro": "ID_ARBITRO"
  },
  {
    "fecha": "2024-05-18",
    "lugar": "Parc des Princes",
    "equipo_local": "ID_EQUIPO",
    "equipo_visitante": "ID_EQUIPO",
    "arbitro": "ID_ARBITRO"
  },
  {
    "fecha": "2024-05-19",
    "lugar": "Etihad Stadium",
    "equipo_local": "ID_EQUIPO",
    "equipo_visitante": "ID_EQUIPO",
    "arbitro": "ID_ARBITRO"
  }
]);

## Entrenadores

db.Entrenadores.insert([
  {
    "nombre": "string",
    "nacionalidad": "string",
    "experiencia": "int"
  },
  {
    "nombre": "Zinedine Zidane",
    "nacionalidad": "Francia",
    "experiencia": 5
  },
  {
    "nombre": "Ronald Koeman",
    "nacionalidad": "Países Bajos",
    "experiencia": 10
  },
  {
    "nombre": "Pep Guardiola",
    "nacionalidad": "España",
    "experiencia": 15
  },
  {
    "nombre": "Hans-Dieter Flick",
    "nacionalidad": "Alemania",
    "experiencia": 20
  },
  {
    "nombre": "Mauricio Pochettino",
    "nacionalidad": "Argentina",
    "experiencia": 12
  }
]);

## Equipos

db.Equipos.insert([
  {
    "nombre": "string",
    "pais": "string",
    "entrenador": "string"
  },
  {
    "nombre": "Real Madrid",
    "pais": "España",
    "entrenador": "Zinedine Zidane"
  },
  {
    "nombre": "FC Barcelona",
    "pais": "España",
    "entrenador": "Ronald Koeman"
  },
  {
    "nombre": "Manchester City",
    "pais": "Inglaterra",
    "entrenador": "Pep Guardiola"
  },
  {
    "nombre": "Bayern Munich",
    "pais": "Alemania",
    "entrenador": "Hans-Dieter Flick"
  },
  {
    "nombre": "Paris Saint-Germain",
    "pais": "Francia",
    "entrenador": "Mauricio Pochettino"
  }
]);

## Resultados

db.resultados.insert([
  {
    "encuentro": {
      "type": "ObjectId",
      "ref": "Encuentros Deportivos"
    },
    "resultado": "string",
    "ganador": {
      "type": "ObjectId",
      "ref": "Equipos"
    }
  },
  {
    "encuentro": "ID_ENCUENTRO",
    "resultado": "3-2",
    "ganador": "ID_EQUIPO"
  },
  {
    "encuentro": "ID_ENCUENTRO",
    "resultado": "1-1",
    "ganador": "EMPATE"
  },
  {
    "encuentro": "ID_ENCUENTRO",
    "resultado": "2-1",
    "ganador": "ID_EQUIPO"
  },
  {
    "encuentro": "ID_ENCUENTRO",
    "resultado": "4-0",
    "ganador": "ID_EQUIPO"
  },
  {
    "encuentro": "ID_ENCUENTRO",
    "resultado": "2-2",
    "ganador": "EMPATE"
  }
]);

## TablaDePosiciones

db.TablaDePosiciones.insert([
  {
    "equipo": {
      "type": "ObjectId",
      "ref": "Equipos"
    },
    "puntos": "int",
    "goles_a_favor": "int",
    "goles_en_contra": "int"
  },
  {
    "equipo": "ID_EQUIPO",
    "puntos": 9,
    "goles_a_favor": 8,
    "goles_en_contra": 3
  },
  {
    "equipo": "ID_EQUIPO",
    "puntos": 7,
    "goles_a_favor": 6,
    "goles_en_contra": 4
  },
  {
    "equipo": "ID_EQUIPO",
    "puntos": 5,
    "goles_a_favor": 4,
    "goles_en_contra": 5
  },
  {
    "equipo": "ID_EQUIPO",
    "puntos": 4,
    "goles_a_favor": 3,
    "goles_en_contra": 4
  },
  {
    "equipo": "ID_EQUIPO",
    "puntos": 1,
    "goles_a_favor": 2,
    "goles_en_contra": 7
  }
]);

## Árbitros 

db.Árbitros.insert([
  {
    "nombre": "string",
    "nacionalidad": "string",
    "experiencia": "int"
  },
  {
    "nombre": "Felix Brych",
    "nacionalidad": "Alemania",
    "experiencia": 10
  },
  {
    "nombre": "Howard Webb",
    "nacionalidad": "Inglaterra",
    "experiencia": 15
  },
  {
    "nombre": "Björn Kuipers",
    "nacionalidad": "Países Bajos",
    "experiencia": 12
  },
  {
    "nombre": "Cüneyt Çakır",
    "nacionalidad": "Turquía",
    "experiencia": 18
  },
  {
    "nombre": "Anthony Taylor",
    "nacionalidad": "Inglaterra",
    "experiencia": 8
  }
]);