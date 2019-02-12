# script-variavel
#!/bin/bash
#criaçao das variaveis locais 
USUARIO="SENAC"
TESTE01=$(test A == B ; echo $?) 
TESTE02=$(test -f /etc/passwd ; echo $?)
USUARIOS=$(who | awk '{print $1}')

#utilizando o comando echo para imprimir na tela os valores das variaveis
#e variaveis especiais do shel
echo "impressao na tela............: ola,mundo!!!"
echo "nome do usuario..............: $USUARIO"
echo "nome do arquivo de shell.....: $0"
echo "quantidade de parametros.....: $#"
echo "todos os parametros..........: $*"
echo "parametro 01.................: $1"
echo "parametro 02.................: $2"
echo "status do comando anterior...: $?"
echo "pid do processo..............: $$"
echo "comando: test A == A.........: $TESTE01"
echo "comando: test -f/etc/passwd..: $TESTE02"
echo "usuarios logados.............: $USUARIOS"

#utilizando o comando if para fazer os testes logicos e
#validar o ambiente
if [ $USUARIO == root ];
then 
	echo "teste de usuarios:.......: usuario e root"
else
	echo "teste de usuario:........: usuario nao e root"
fi	

#utilizando o comando if encadeado para aumentar a qualidade dos 
#testes logicos
if [ $TESTE01 -eq 0 ];
then
	echo "resultado do comando test e.....: VERDADEIRO"
elif [ $TESTE01 -eq 1 ];
then 
	echo "resultado do comando test e.....: FALSO"
fi	

#utilizando o comando case ára fazer os testes logicos 
#e validar o ambiente 
case $TESTE01 in 
	0) echo "resultado do comando case e..: 0 - VERDADEIRO";;
	1) echo "resultado do comando case e..: 1 - FALSO";;
	*) echo "resultado do comando case e..:   NAO INDENTIFICADO";;
esac	

#utilizando o comando read para receber os
#valores e fazer o teste logico com case
read -p "digite as letras: A, B ou C......: " LETRAS;
case $LETRAS in
	A|a) echo "A letra digitada foi.......: $LETRAS";;
	B|b) echo "A letra digitada foi.......: $LETRAS";;
	C|c) echo "A letra digitada foi.......: $LETRAS";;
	  *) echo "A letra digitada errada....: $LETRAS"
esac	 			 
	  
#utilizando o laço de loop for para verificar os numeros digitados 
#junto com o comando read 
read -p "uma sequencia de numeros.........: " NUMEROS;
for VALORES in $NUMEROS;
do 
	echo "numeros passados para o loop....: $VALORES"
done

#utilizando o laço de loop for para gerar uma tabuada junto com o 
#comando read
read -p "digite um numero da tabuada......: " NUMERO;
for TABUADA in $(seq 0 10);
do 
	echo "$NUMERO X $TABUADA .............: $(($TABUADA * $NUMERO))"
done

#Utilizando o laço de loop while para alcançar os valores
#desejados com o comando read
read -p "digite um numero de inicio.......: " INICIO;
read -p "digite um numero de fim..........: " FIM;
while [ $INICIO -le $FIM ];
do
	echo "valor de sequencia numerica.....: $INICIO"
	let INICIO=INICIO+1
done 



















































	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
