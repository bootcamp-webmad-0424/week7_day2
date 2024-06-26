# MongoDB queries cheatsheet


````javascript

// basic queries

{ year: '1994' }

{ _id: ObjectId('5c6a9f45b975fde86574b6a7') }







// Comparison operators

{ year: { $eq: '1995' } }

{ year: { $gt: '1995' } }

{ year: { $gte: '1995' } }

{ year: { $lt: '1995' } }

{ year: { $lte: '1995' } }

{ year: { $ne: '1994' } }       // De año diferente al 94







// Logic operators 

{ $or: [{ year: '1995' }, { year: '1997' }] }                       // Del año 95 o del 97

{ $or: [{ year: { $gte: '2000' } }, { genre: 'Fantasy' }] }         // A partir del 2000 o de fantasía

{ $and: [{ year: '1995' }, { rate: { $gt: '8' } }] }                // Del año 95 y con más de un 8

{ $and: [{ year: { $gt: '1995' } }, { year: { $lt: '1999' } }] }     // Del año 96 al 98

{ $nor: [{ year: '1995' }, { director: 'Christopher Nolan' }] }      // Ni del año 95 ni dirigida por C.N.






// Array logic operators 

{ genre: 'Drama' }                              // Todas las de drama

{ genre: { $in: ["Drama", "Fantasy"] } }        // Cualquiera de drama o fantasía

{ genre: { $nin: ["Drama", "Horror"] } }        // Ninguna de drama u horror

{ genre: { $all: ["Drama", "Horror"] } }        // Todas con drama y horror







// Nested objects

{'address.zipcode': "10462"}            // Registros con su adress.zipcode igual a 10462




// Nested arrays

{'grades.score': 10} 

{'grades.grade': 'A'} 

{'grades.score': { $gt: 7 }} 

{ grades: { $elemMatch: { grade: "A", score: { $gt: 15 } } } }      // Todos los grades con alguno de 'grade' A  y 'score' > de 15




// Element Query Operators

 { cuisine: { $exists: true} }





 // EXTRA: projections

{ name: 1, cuisine: 1 }



// Sort

{ name: 1 }
````
