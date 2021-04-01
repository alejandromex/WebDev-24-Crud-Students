# Desing Document

### Celta class implementation





Name: Alejandro Velazquez

Date: 2021/01/04

Description:

- This document redact a new form to exec query commands (RawQuerys or StoreProcedures) to make the code more clean and dont mix the SQL commands with the programming lang (WL, Js, etc..)



How:

* We change:

  * 	sSName = "Nombre";
    	sSurname ="Apellido";
    	sAge = "Edad";
    	sGender= "Genero"
    	
    	sqlCommand = "INSERT 
    			INTO estudiantes_dev (nombre, apellido, edad, genero) 
    			VALUES (sName+","+sSurname"+", "+sAge+","+@apellido+", "+sAge+", "+sGender +");"
    	IF HExecuteSQLQuery(ds, connectionToDb, hQueryWithoutCorrection, sQlCommand) THEN
    		RESULT ds;
    	END

  To:

  * 	arrParams is array of strings;
    	arrParams.Add(:m_name);
    	arrParams.Add(:m_surname);
    	arrParams.Add(:m_age+"");
    	arrParams.Add(:m_gender);
    	Celta.ExecuteCommand("CreateANewStudent",STOREPROCEDURE,_INSERT,arrParams);



​	This type of consults separe the sql format from the pLenguage

[Method Celta]([WebDev-24-Crud-Students/Celta-ExecuteSQLCmd.txt at main · alejandromex/WebDev-24-Crud-Students (github.com)](https://github.com/alejandromex/WebDev-24-Crud-Students/blob/main/Celta-ExecuteSQLCmd.txt))

[full project]([alejandromex/WebDev-24-Crud-Students: My first app with the tool WebDev 24 (github.com)](https://github.com/alejandromex/WebDev-24-Crud-Students))

