# Note Taker

In this project I utilized that existing code that was given to create a wepage that has a corrisponding database that will log the information
that is given to it via that adding and saving buttons. I added the routes that would be used for each page of it and direct it to the proper page.
I also created a apie/notes routes. 

I used insomnia to verify that I was doing the proper get and push commands and dealing with the information properly. By using that I was able to 
understand what was being returned and add the new notes to the existing database and return that database back to the javascipt side of the code. 


## Authors

- [@marshallrizzuto](https://github.com/Zoot83)


Website: https://github.com/Zoot83/Note_Taker
## Features

- Node
- Heroku
- File System 
- Writing to File 
- Packages
- Npm
- Routers
- Databases
- Express
- Insomnia 


## Usage/Examples

  

To ensure that the new notes were added to the database and put inside the proper array I would read from the database and pull all the information out of it.
Then I would add the new note to that array at the last position and then return that array to the database. Below is an example of the code that I used. 


    const readFromFile = util.promisify(fs.readFile);

    const writeToFile = (destination, content) =>
         fs.writeFile(destination, JSON.stringify(content, null, 4), (err) =>
    err ? console.error(err) : console.info(`\nData written to ${destination}`)
    );

    const readAndAppend = (content, file) => {
    fs.readFile(file, 'utf8', (err, data) => {
    if (err) {
      console.error(err);
    } else {
      const parsedData = JSON.parse(data);
      parsedData.push(content);
      writeToFile(file, parsedData);
    }
    });
    };