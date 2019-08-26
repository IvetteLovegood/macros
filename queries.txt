//////////////////////////////////////////////////////////////////////////////////////////

// CREDITO
FROM [Master General]
WHERE ((([Master General].Estatus)=50));

//ANALISTA
FROM [Master General]
WHERE ((([Master General].[Fecha Analisis])=Date()) AND (([Master General].[Analista 1])=IIf([Forms]![Mesa de Recepción]![Puesto]<>"Supervisor",[Forms]![Mesa de Recepción]![Analista])) AND (([Master General].[Analista 2]) Is Null)) OR ((([Master General].[Fecha Analisis])=Date()) AND (([Master General].[Analista 2])=IIf([Forms]![Mesa de Recepción]![Puesto]<>"Supervisor",[Forms]![Mesa de Recepción]![Analista])));

//////////////////////////////////////////////////////////////////////////////////////////

// MESA DE TRABAJO ESPEJO

//Sugerencia ventas Anuales 

SELECT [Catalogo Giros Comerciales].Anual, [Catalogo Giros Comerciales].MCC
FROM [Catalogo Giros Comerciales]
GROUP BY [Catalogo Giros Comerciales].Anual, [Catalogo Giros Comerciales].MCC, [Catalogo Giros Comerciales].Anual
HAVING ((([Catalogo Giros Comerciales].MCC)=[Forms]![Mesa de Trabajo_Espejo]![Giro comercial Sugerido]))
ORDER BY [Catalogo Giros Comerciales].Anual DESC;


//A/T

SELECT [Catalogo Giros Comerciales].[A/T], [Catalogo Giros Comerciales].MCC
FROM [Catalogo Giros Comerciales]
WHERE ((([Catalogo Giros Comerciales].MCC)=[Forms]![Mesa de Trabajo_Espejo]![Giro comercial Sugerido]))
ORDER BY [Catalogo Giros Comerciales].[A/T] DESC;


//////////////////////////////////////////////////////////////////////////////////////////


// MESA TRABAJO ANALISTA

//Sugerencia ventas Anuales 

SELECT [Catalogo Giros Comerciales].Anual, [Catalogo Giros Comerciales].MCC
FROM [Catalogo Giros Comerciales]
GROUP BY [Catalogo Giros Comerciales].Anual, [Catalogo Giros Comerciales].MCC, [Catalogo Giros Comerciales].Anual
HAVING ((([Catalogo Giros Comerciales].MCC)=[Forms]![Mesa de Trabajo_Analista]![Giro comercial Sugerido]))
ORDER BY [Catalogo Giros Comerciales].Anual DESC;


//A/T

SELECT [Catalogo Giros Comerciales].[A/T], [Catalogo Giros Comerciales].MCC
FROM [Catalogo Giros Comerciales]
WHERE ((([Catalogo Giros Comerciales].MCC)=[Forms]![Mesa de Trabajo_Analista]![Giro comercial Sugerido]))
ORDER BY [Catalogo Giros Comerciales].[A/T] DESC;


//////////////////////////////////////////////////////////////////////////////////////////


// MESA TRABAJO CREDITO 

// Sugerencias ventas Anuales

SELECT [Catalogo Giros Comerciales].Anual, [Catalogo Giros Comerciales].MCC
FROM [Catalogo Giros Comerciales]
GROUP BY [Catalogo Giros Comerciales].Anual, [Catalogo Giros Comerciales].MCC, [Catalogo Giros Comerciales].Anual
HAVING ((([Catalogo Giros Comerciales].MCC)=[Forms]![Mesa de Trabajo_Credito]![Giro comercial Sugerido]))
ORDER BY [Catalogo Giros Comerciales].Anual DESC;

//A/T 

SELECT [Catalogo Giros Comerciales].[A/T], [Catalogo Giros Comerciales].MCC
FROM [Catalogo Giros Comerciales]
WHERE ((([Catalogo Giros Comerciales].MCC)=[Forms]![Mesa de Trabajo_Credito]![Giro comercial Sugerido]))
ORDER BY [Catalogo Giros Comerciales].[A/T] DESC;

