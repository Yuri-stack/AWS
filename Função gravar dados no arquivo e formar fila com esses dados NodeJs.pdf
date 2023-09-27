Função gravar dados no arquivo e formar fila com esses dados NodeJs

```
//esse metodo esta pegando os dados do usuario invluindo
 async gravar(x: UsuarioCadastrarDto){

    var arquivo ;//variavel arquivo

    try {

      //variável arquivo recebe o fs.readFileSync para fazer leitura dos dados do arquivo.json
      arquivo = fs.readFileSync('arquivo.json', {encoding:'UTF8', flag:'r'})
      

      //isso aqui é só p vc ver o que esta acontecendo pode remover as proximas linhas
      console.log("aqui os dados do arquivo")

      console.log(typeof arquivo)//tipo dos dados que recuperamos no objeto

      console.log(arquivo)//aqui podemos ver os dados como estamos recebendo      

    } catch (err) {

    console.error(err)//caso de erro na ação ele exibe o erro

    }

    //data
    let dia = new Date

    //criar o objeto  e aplicar os valores dentro do objeto Usuario com dados que esta sendo enviado pelo postman ou insomnia
    let usuario = new banco_user()

  	usuario.email = x.email
    usuario.nome = x.nome
    usuario.createdAt = dia

    //criar um objeto queue
    let  queue = [];   

    //passando o valor recuperado no arquivo em formato json para o nosso objeto queue 
    queue.push(JSON.parse(arquivo));    

    //contante com o objeto usuário -- registros que estão sendo enviados agora sendo passada para a constante aqui
    const aqui  = ({email:usuario.email, nome:usuario.nome, dia: usuario.createdAt});

    //a constante aqui esta sendo adicionada no objeto queue
    queue.push(aqui)

    //apenas para ver e entender o que esta acontecendo aqui você vai ver o formato dos dados da constante aqui
    console.log(typeof aqui)

    //apenas para ver e entender aqui esta o conteúdo do queue
    console.log(queue)

    //recebido os dados do usuário e tbm informada a data atual
    const convert = JSON.stringify(queue)

    //console.log(convert);
      fs.writeFile("arquivo.json", convert, (err) => {        

        if (err) throw err;
        console.log(typeof convert);

      });

      //vamos utilizar a biblioteca do node que grava arquivos e passaremos data time para o nome do arquivo, dados do usuario para dentro do arquivo e geramos o arquivo
}

//fim metodo gravar no arquivo
```

