|| Código INDEX


const Discord = require('discord.js') //Descargamos el paquete ''discord.js''//

const client = new Discord.Client() //Definimos el bot para poder loguearnos con él//

const { Client, MessageEmbed, Guild } = require('discord.js');

require('dotenv').config();


client.on('message', (message) => { //Abrimos una llave para que nuestro bot pueda hablar//
  let prefix = '!' //Debemos añadirle el prefijo que queremos para que el bot pueda ejecutar el comando, en mi caso he puesto un ''!''.//

  if(message.author.bot) return; //Con esto estamos haciendo que nuestro bot no ejecute su comando si se lo dice otro bot.//

  if(!message.content.startsWith(prefix)) return; //Estamos diciéndole al bot que no ejecute su comando si no tiene el prefijo delante//

  let usuario = message.mentions.members.first() || message.member; //Definimos al autor del mensaje//
  const args = message.content.slice(prefix.length).trim().split(/ +/g);
  const command = args.shift().toLowerCase();

  if(command === 'hola'){ //Debemos hacer una prueba de comando. En este caso, el comando sería !hola//
    message.channel.send("Adiós!") //Hacemos que el bot diga ''Adiós!'' cuando se escriba !hola.//
  }

}) //Cerramos la llave//


const mySecret = process.env['TOKEN'] //Necesitaremos el token y lo definiremos en ''secrets''//
client.login(mySecret) //Esto hace que el bot se loguee con el token que hemos definido.//

|| Las demás cosas las explico en el video, así que estad atentos 😄
