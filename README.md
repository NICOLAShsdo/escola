19. Testando Cadastro de Professores:

Comando: curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\":
\"07494812857\"}"

Resposta: {"nome":"Henrique Louro", "email":"henrique.louro@fatec.sp.gov.br", "cpf":"07494812857",
"_id":"682fa1b2c3d4e5f67890abcd","__v":0}

Comando: curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"nome\": \"Carlos Silva\", \"email\": \"carlos.silva@fatec.sp.gov.br\", \"cpf\": \" 63479695051\"}"

Resposta: {"nome":"Carlos Silva", "email":"carlos.silva@fatec.sp.gov.br", "cpf":"63479695051",
"_id":"682f9c8e1a2b3d4f5e6a7b8c","__v":0}

Comando: curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"nome\": \"Odete Roitman\", \"email\": \"odete.roitman@fatec.sp.gov.br\", \"cpf\": \"
32082128016\"}"

Resposta: {"nome":"Odete Roitman", "email":"odete.roitman@fatec.sp.gov.br", "cpf":"32082128016",
"_id":"682f3e7c9d1a0b2c3f4e5a6d","__v":0}

20. Testando Unique no Cadastro de Professores:
    
Comando: curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\":
\"07494812857\"}"

Resposta: {"message":"CPF ou e-Mail já em uso"}

22. Testando validação do CPF:
    
Comando: curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\":
\"12345678910\"}"

Resposta: {"message":"12345678910 não é um CPF válido"}

22. Testando validação do e-Mail:

Comando: curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec\", \"cpf\": \"12345678910\"}"

Resposta: {"message":"henrique.louro@fatec não é um formato de e-mail válido"}

23. Listando Professores:

Comando: curl.exe -X GET http://localhost:3001/professor

Resposta: [{"_id":"682fbcde9012a3f4b56789cd","nome":"Henrique Louro",
"email":"henrique.louro@fatec.sp.gov.br",
"cpf":"07494812857","__v":0},{"_id":"682f76543210fedcba987654","nome":"Carlos Silva",
"email":"carlos.silva@fatec.sp.gov.br", "cpf":"63479695051","__v":0},
{"_id":"682f0a1b2c3d4e5f6a7b8c9d","nome":"Odete Roitman",
"email":"odete.roitman@fatec.sp.gov.br","cpf":"32082128016","__v":0}]

25. Update Professor:

Comando: curl.exe -X PUT http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"id\":\"682f669ff4bd0fb518a18a2e\",\"nome\": \"Odetinha Roitman\", \"email\":
\"odetinha.roitman@fatec.sp.gov.br\", \"cpf\": \" 32082128016\"}"

Resposta: {"_id":"e12ac34f9d8b7e60fa31bc45","nome":"Odetinha Roitman",
"email":"odetinha.roitman@fatec.sp.gov.br", "cpf":"32082128016","__v":0}

26. Deletando Professor:

Comando: curl.exe -X DELETE http://localhost:3001/professor -H "Content-Type: application/json" -d
"{\"id\":\"6838fbf8c034206db669a3b2\"}"

Resposta: {"message":"Professor excluído com sucesso"}

27. Listando Professores novamente:

Comando: curl.exe -X GET http://localhost:3001/professor

Resposta: [{"_id":"682f3210fedcba9876543210","nome":"Henrique
Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},{"_id":"682f45a6b7c8d9e0
f1a2b3c4","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0}]

27. Testando Cadastro de Disciplinas:

Comando: curl.exe -X POST http://localhost:3001/disciplina -H "Content-Type: application/json" -d
"{\"descricao\": \"Técnicas de Programação II\"}"

Resposta: {"descricao":"Técnicas de Programação II","_id":"682f8e7d6c5b4a3928172635","__v":0}

Comando: curl.exe -X POST http://localhost:3001/disciplina -H "Content-Type: application/json" -d
"{\"descricao\": \"Lógica de Programação\"}"

Resposta: {"descricao":"Lógica de Programação","_id":"682f8e7d6c5b4a3928172635","__v":0}

28. Listando as Disciplinas:

Comando: curl.exe -X GET http://localhost:3001/disciplina

Resposta: [{"_id":"682f1a2b3c4d5e6f7890abcd","descricao":"Técnicas de Programação
II","__v":0},{"_id":"682fa9b8c7d6e5f412345678","descricao":"Lógica de Programação","__v":0}]

29. Associando Professores às Disciplinas:

Comando: curl.exe -X POST http://localhost:3001/professor_has_disciplina -H "Content-Type:
application/json" -d "{\"professor\": \"682f3210fedcba9876543210\", \"disciplina\":
\"682fbdac9e8d7c6b5a432110\"}"

Resposta: {"professor":"682f0f0e1d2c3b4a59687766", "disciplina":"682fbdac9e8d7c6b5a432110",
"_id":"682f9a8b7c6d5e4f3210abcd","__v":0}

Comando: curl.exe -X POST http://localhost:3001/professor_has_disciplina -H "Content-Type:
application/json" -d "{\"professor\": \"682fa1b2c3d4e5f67890abcd\", \"disciplina\":
\"682fa1b2c3d4e5f67890abcd\"}"

Resposta: {"professor":"682f123456abcdef7890abcd", "disciplina":"682fa1b2c3d4e5f69876dcba",
"_id":"682fb2c3d4e5f6a7890abc12","__v":0}

30. Listando Professores e Disciplinas

Comando: curl.exe -X GET http://localhost:3001/professor_has_disciplina

Resposta:
[{"_id":"682f0987654321fedcba8765","professor":{"_id":"682f0987654321fedcba8765","nome":"Henrique
Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},"disciplina":{"_id":"682fa
bcdefabcdef12345678","descricao":"Técnicas de Programação II","__v":0}},
{"_id":"682f0a1b2c3d4e5f60718293","professor":{"_id":"682f4c3b2a1908e7d6c5b4a3","nome":"Carlos
Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0},"disciplina":{"_id":"682f7654
3210fedcba987612","descricao":"Lógica de Programação","__v":0}}]
