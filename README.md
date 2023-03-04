# accsc560assign4.2

//Code is down below
//Make sure to view in "raw" after clicking on the "readme" file to see correct spacing of code

/* Alex Cayer 3-2-2023 CSC 560 Assign 4.2 */
/* Purpose of the program (all in frontend folder): To try to add, update, and delete curlingbio players from the csc560a3p2new4 folder. */
/* Files down below */

/* styles.scss */

/* You can add global styles to this file, and also import other style files */
@import 'main-styles';
@import '../node_modules/bulma/bulma.sass';

//main-styles.scss file down below
@import url('https://fonts.googleapis.com/css?family=Lato:400,700|Nunito:400,700');

$turquoise: #44ddd0;
$green: #27d7a1;
$light-green: #45f69e;
$dark-green: rgb(0, 100, 80);

$light: #f8f8f8;

//Allows for "Bulma's global variables" to change so they are current (Devstackr, 2019).
$family-sans-serif: "Nunito", sans-serif;
$primary: $green;

$link: $turquoise;

//Allows for Bulma's component variables to be up to date (Devstackr, 2019).
$control-border-width: 2px;
$input-boder-color: transparent;
$input-shadow: none;

//Allows for the "custom global systles (will be applied to whole app)" to be applied (Devstackr, 2019).

html {
    background: linear-gradient(to right top, $turquoise, $green);
}

html, body {
    height:100%;
}

.centered-content {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
}

// pages/player-view folders down below.
<!--players-view.component.html file below-->

<div class="centered-content">
    <div class="players-manager-container">

        <div class="sidebar has-background-white">
            <h1 class="title has-text-primary">
                Players
            </h1>

            <div class="players-menu">
                <a class="players-menu-item is-active">
                    <p>Player #1</p>
                </a>
                <a class="players-menu-item">
                    <p>Player #2</p>
                </a>
                <a class="players-menu-item">
                    <p>Player #3</p>
                </a>
            </div>

            <button class="button is-primary has-text-white" routerLink="/new-player">+ New Player</button>
        </div>

        

        <div class="players-infolist-container has-background-light">
            <div class="top-bar">
                <h1 class="title has text-primary">
                    Curlingbio
                </h1>
                <div class="dropdown is-hoverable is-right">
                    <div class="dropdown-trigger">
                        <button class="button" aria-haspopup="true">
                            <span>Settings</span>
                            <span class="icon is-small">
                                <i class="fas fa-angle-down" aria-hidden="true"></i>
                            </span>
                        </button>
                    </div>
                    <div class="dropdown-menu" id="dropdown-menu4" role="menu">
                        <div class="dropdown-content">
                            <a routerLink="/edit-player" class="dropdown-item">
                                Edit
                            </a>
                            <a href = "#" class="dropdown-item has-text-danger">
                                <!--Would remove href if decide to delete player as noted in Devstackr's 14th video tutorial (Devstackr, 2019)-->
                                Delete
                            </a>
                        </div>
                    </div>
                </div>
            </div>
            


            <!--Curlingbio Elements-->
            <div class="curlingbio">
                <p>name: </p>
            </div>
            <div class="curlingbio">
                <p>age: </p>
            </div>
            <div class="curlingbio">
                <p>gender: </p>
            </div>
            <div class="curlingbio">
                <p>position: </p>
            </div>
            <div class="curlingbio">
                <p>teamname: </p>
            </div>
            <div class="curlingbio">
                <p>totalthrowsthatstayinplay: </p>
            </div>
            <div class="curlingbio">
                <p>totaleliminatethrows: </p>
            </div>
            <div class="curlingbio">
                <p>sweepturnspergame: </p>
            </div>
            <div class="curlingbio">
                <p>teamwins: </p>
            </div>
            <div class="curlingbio">
                <p>yearsofexperience: </p>
            </div>

        </div>



    </div>
</div>

//players-view.component.css down below
//Purpose of this file: To create the styles regarding players-view.
@import '../../../main-styles.scss';


.players-manager-container {
    display: flex;
    width: 100%;
    height: 100%;
    max-width: 2000px;
    max-height: 2500px;
}

.sidebar {
    display: flex;
    flex-direction: column;

    width: 250px;
    background: white;

    padding: 42px;

    border-top-left-radius: 8px;
    border-bottom-left-radius: 8px;
}

.players-infolist-container {
    display: flex;
    flex-direction: column;
    flex-grow: 1;

    border-radius: 8px;
    padding: 42px;

    border-top-right-radius: 8px;
    border-bottom-right-radius: 8px;


    .top-bar {
        margin-bottom:20px;
        display: flex;
        .title {
            flex-grow: 1;
            margin: 0;
        }
    }
}

.title {
    font-family: 'Lato';
    font-size: 24px;
    text-transform: uppercase;
    letter-spacing: 2px;
}

.players-menu {

    display: flex;
    flex-direction: column;
    margin-top: 15px;
    flex-grow: 1;

    .players-menu-item{
        display: flex;

        align-items: center;
        padding: 10px 15px;
        border-radius: 5px;

        width: 100%;
        color: #5f5f5f;
        margin-bottom: 5px;

        &:hover{
            background: $light;
        }

        &.is-active {
            background-color: #cff8ef;
            color:$dark-green;
        }

    }

}

.curlingbio {
    background: white;
    padding: 15px 20px;
    border-radius: 5px;
    margin-top: 10px;

    transition: box-shadow 0.2s ease;

    &:hover {
        box-shadow: 0 0 0 5px #eeeeee;
    }
}


//players-view.component.spec.ts file down below
import { ComponentFixture, TestBed } from '@angular/core/testing';

import { PlayersViewComponent } from './players-view.component';

describe('PlayersViewComponent', () => {
  let component: PlayersViewComponent;
  let fixture: ComponentFixture<PlayersViewComponent>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [ PlayersViewComponent ]
    })
    .compileComponents();

    fixture = TestBed.createComponent(PlayersViewComponent);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });

  it('should create', () => {
    expect(component).toBeTruthy();
  });
});

//players-view.component.ts file down below
import { Component, OnInit } from '@angular/core';
import { CurlingbioService } from 'src/app/curlingbio.service';

@Component({
  selector: 'app-players-view',
  templateUrl: './players-view.component.html',
  styleUrls: ['./players-view.component.scss']
})
export class PlayersViewComponent implements OnInit {
  constructor(private curlingbioService: CurlingbioService) { }
  //would eventually change to constructor(private curlingbioService: CurlingbioService, private route: ActivatedRoute, private router: Router) { }
  //Contains players in a container
  //players: Player[];

  //selectedPlayerId: string;

  ngOnInit() {
    //Below is what I would write if I was able to follow Devstackr's 5th video tutorial to help me how to set up new player
    // this.route.params.subscribe(
      //(params: Params) => {
          //this.selectedPlayerId = params.selectedplayerId;
          //this.curlingbioService.getPlayers(params.curlingbioId).subscribe((players: Players []) =>
                //this.curlingbio = curlingbio;
          //)}
        //} else {
            //this.players = undefined;
        //}
      //}
    //)

    //if I was able to get and follow similar steps to like in Devstackr's tutorial series
    //this.curlingbioService.getPlayers().subscribe((players: Player[]) => {
        //this.players = players;
    //})

  }

  //createNewPlayers() {

    //testing statement of this.curlingbioService.createPlayers('Testing Testing', 30, 'male', 'SubLead', 'Mario_rink', 8, 4, 0, 10, 8).subscribe((response: any) = >
    //{ console.log(response); }); 
    //does work. So, can add player manually like this!

    

    //});

//}
  //Deleting user if I could add players from new-player.component.html properly.
  //onDeletePlayerClick() {
    //this.curlingbioService.deletePlayer(this.selectedPlayerId).subscribe((res: any) => {
      //this.router.navigate(['/players']);
      //console.log(res);
      
    //})
  //}

  
}

//app.module.ts file down below
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { PlayersViewComponent } from './pages/players-view/players-view.component';

import { HttpClientModule } from '@angular/common/http';
import { NewPlayerComponent } from './pages/new-player/new-player.component';
import { EditPlayerComponent } from './pages/edit-player/edit-player.component';

@NgModule({
  declarations: [
    AppComponent,
    PlayersViewComponent,
    NewPlayerComponent,
    EditPlayerComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    HttpClientModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

//curlingbio.service.ts down below
import { Injectable } from '@angular/core';
import { WebRequestService } from './web-request.service';

@Injectable({
  providedIn: 'root'
})
export class CurlingbioService {

  constructor(private webReqService: WebRequestService) { }

  createPlayers(name: string, age: Number, gender: string, position: string, teamname: string, totalthrowsthatstayinplay: Number, totaleliminatethrows: Number, sweepturnspergame: Number, teamwins: Number, yearsofexperience: Number) {
    //We want to send a web request to create a player
    return this.webReqService.post('curlingbio', {name, age, gender, position, teamname, totalthrowsthatstayinplay, totaleliminatethrows, sweepturnspergame, teamwins, yearsofexperience});

  }

  //how updatePlayers would work down below if I was able to complete the adding player step under new-player.component.html
  // updatePlayers(id: string, name: string, age: Number, gender: string, position: string, teamname: string, totalthrowsthatstayinplay: Number, totaleliminatethrows: Number, sweepturnspergame: Number, teamwins: Number, yearsofexperience: Number) {
    //return this.webReqService.patch(`curlingbio/${id}`, {name, age, gender, position, teamname, totalthrowsthatstayinplay, totaleliminatethrows, sweepturnspergame, teamwins, yearsofexperience}  )
  //}

  //if deletePlayers would work code in comments below
  //deletePlayers(id: string) {
      //return.this.webReqService.delete('curlingbio/${id}');
  //}
  

//web-request.service.ts down below
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
//Purpose of this file: "to wrap all of our request methods to
//make it a bit neater and provide the root URL as a constant here
//and then use it in the requests," so they can "return the observables
//that these HTTP methods return" (Devstackr, 2019).
@Injectable({
  providedIn: 'root'
})
export class WebRequestService {

  readonly ROOT_URL;

  constructor(private http: HttpClient) { 
    //Utilized 127.0.0.1:8080 over localhost:8080 due to the fact I wanted to match
    //the csc560a3p2new4 index4.js file with the dbPath.
    //Didn't work: http://127.0.0.1:8080/api/curlingbio
    //Link that did work: 'http://127.0.0.1:8080/api/';

    this.ROOT_URL = 'http://127.0.0.1:8080/api/';
  }

  get(uri: string) {
    return this.http.get(`${this.ROOT_URL}/${uri}`);


  }

  post(uri: string, payload: Object) {
    return this.http.post(`${this.ROOT_URL}/${uri}`, payload);
  }

  patch(uri: string, payload: Object) {
    return this.http.patch(`${this.ROOT_URL}/${uri}`, payload);
  }

  delete(uri: string) {
    return this.http.delete(`${this.ROOT_URL}/${uri}`);

  }
}

// pages/new-player files down below
<!--new-player.component.html file down below-->
<div class="centered-content">
    <div class="modal-box">
        <h1 class="title">
            Create a new player
        </h1>

        <!--Did also try to put in "player", "players", and "curlingbio" 
            followed by title of string or numberInput 
            but still resulted in Property error. Ex: #playerNameInput -->
        <!--Also, did try to do #name, #age, #gender,
        #position, #teamname, #totalthrowsthatstayinplay, 
        #totaleliminatethrows, #sweepturnspergame, #teamwins, and
        #yearsofexperience in addition to having Input at the end for template variables and set to .value 
        but this resulted in more errors such as HTTPInputElement can't be assigned to string type and Number type-->

        <input class="input has-has-background-light is-medium" type="text" placeholder="List name of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List age of player...">
        <input class="input has-has-background-light is-medium" type="text" placeholder="List gender of player...">
        <input class="input has-has-background-light is-medium" type="text" placeholder="List position of player...">
        <input class="input has-has-background-light is-medium" type="text" placeholder="List teamname of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for totalthrowsthatstayinplay of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for totaleliminatethrows of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for sweepturnspergame of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for teamwins of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for yearsofexperience of player...">
        


        <!-- Comments in green down below represent attempts at trying to write and execute multiple 
            template reference variables in addition to utilizing mutiple. These haven't worked yet no matter
             changing the first part to before each input to "player", "curlingbio", and "players" -->

        <!-- <input #playerNameInput, playerAgeInput, playerGenderInput, playerPositionInput, playerTeamnameInput, playerTotalthrowsthatstayinplayInput, playerTotaleliminatethrowsInput, playerSweepturnspergameInput, playerTeamwinsInput, playerYearsofexperienceInput class="input has-background-light is-medium" type="text, Number, text, text, text, Number, Number, Number, Number" placeholder="Enter name, age, gender, position, teamname, totalthrowsthatstayinplay, totaleliminatethrows, sweepturnspergame, teamwins, and yearsofexperience..."> -->
        <br><br>
        <div class="buttons is-right">
            <button class="button is-medium" routerLink="/">Cancel</button>
            <button class="button is-primary has-text-white is-medium">Create</button>
            <!--<button class="button is-primary has-text-white is-medium" (click)="createPlayers(playersNameInput.value, playersAgeInput.value, playersGenderInput.value, playersPositionInput.value, playersTeamnameInput.value, playersTotalthrowsthatstayinplayInput.value, playersTotaleliminatethrowsInput.value, playersSweepturnspergameInput.value, playersTeamwinsInput.value, playersYearsofexperienceInput.value)">Create</button>-->
        </div>

    </div>
</div>

// new-player.component.scss file down below
.modal-box {
    min-height: 280px;
    width: 100%;
    max-width: 580px;
    background: white;
    border-radius: 5px;
    padding: 35px;
}

//new-player.component.spec.ts down below
import { ComponentFixture, TestBed } from '@angular/core/testing';

import { NewPlayerComponent } from './new-player.component';

describe('NewPlayerComponent', () => {
  let component: NewPlayerComponent;
  let fixture: ComponentFixture<NewPlayerComponent>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [ NewPlayerComponent ]
    })
    .compileComponents();

    fixture = TestBed.createComponent(NewPlayerComponent);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });

  it('should create', () => {
    expect(component).toBeTruthy();
  });
});

//new-player.component.ts down below
import { Component, OnInit } from '@angular/core';
import { CurlingbioService } from 'src/app/curlingbio.service';

@Component({
  selector: 'app-new-player',
  templateUrl: './new-player.component.html',
  styleUrls: ['./new-player.component.scss']
})
export class NewPlayerComponent implements OnInit {

  constructor(private curlingbioService: CurlingbioService) { }

  ngOnInit() {

  }

  createPlayers(name: string, age: Number, gender: string, position: string, teamname: string, totalthrowsthatstayinplay: Number, totaleliminatethrows: Number, sweepturnspergame: Number, teamwins: Number, yearsofexperience: Number) {
    this.curlingbioService.createPlayers(name, age, gender, position, teamname, totalthrowsthatstayinplay, totaleliminatethrows, sweepturnspergame, teamwins, yearsofexperience).subscribe((response: any) => {
      console.log(response);
    });
  }

}

// pages/edit-player files down below (wanted to fill out but because of errors from new-player, was unable to complete this part. 
// but was able to get it partially set up and can be changed if I had more time.
<!--edit-player.component.html file down below -->
<div class="centered-content">
    <div class="modal-box">
        <h1 class="title">
            Edit an existing player
        </h1>

        <!--Did also try to put in "player", "players", and "curlingbio" 
            followed by title of string or numberInput 
            but still resulted in Property error. Ex's: #playerNameInput, #curlingbioNameInput -->
        <!--Also, did try to do #name, #age, #gender,
        #position, #teamname, #totalthrowsthatstayinplay, 
        #totaleliminatethrows, #sweepturnspergame, #teamwins, and
        #yearsofexperience in addition to having Input at the end for template variables and set to .value 
        but this resulted in more errors such as HTTPInputElement can't be assigned to string type and Number type-->

        <input class="input has-has-background-light is-medium" type="text" placeholder="List name of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List age of player...">
        <input class="input has-has-background-light is-medium" type="text" placeholder="List gender of player...">
        <input class="input has-has-background-light is-medium" type="text" placeholder="List position of player...">
        <input class="input has-has-background-light is-medium" type="text" placeholder="List teamname of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for totalthrowsthatstayinplay of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for totaleliminatethrows of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for sweepturnspergame of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for teamwins of player...">
        <input class="input has-has-background-light is-medium" type="number" placeholder="List number for yearsofexperience of player...">
        


        <!-- Comments in green down below represent attempts at trying to write and execute multiple 
            template reference variables in addition to utilizing mutiple. These haven't worked yet no matter
             changing the first part to before each input to "player", "curlingbio", and "players" -->

        <!-- <input #playerNameInput, playerAgeInput, playerGenderInput, playerPositionInput, playerTeamnameInput, playerTotalthrowsthatstayinplayInput, playerTotaleliminatethrowsInput, playerSweepturnspergameInput, playerTeamwinsInput, playerYearsofexperienceInput class="input has-background-light is-medium" type="text, Number, text, text, text, Number, Number, Number, Number" placeholder="Enter name, age, gender, position, teamname, totalthrowsthatstayinplay, totaleliminatethrows, sweepturnspergame, teamwins, and yearsofexperience..."> -->
        <br><br>
        <div class="buttons is-right">
            <button class="button is-medium" routerLink="/">Cancel</button>
            <button class="button is-primary has-text-white is-medium">Save</button>
            <!--<button class="button is-primary has-text-white is-medium" (click)="createPlayers(playersNameInput.value, playersAgeInput.value, playersGenderInput.value, playersPositionInput.value, playersTeamnameInput.value, playersTotalthrowsthatstayinplayInput.value, playersTotaleliminatethrowsInput.value, playersSweepturnspergameInput.value, playersTeamwinsInput.value, playersYearsofexperienceInput.value)">Create</button>-->
        </div>

    </div>
</div>

//Nothing in edit-player.component.scss file. Going on to the next file in the edit-player folder.

//edit-player.component.spec.ts down below
import { ComponentFixture, TestBed } from '@angular/core/testing';

import { EditPlayerComponent } from './edit-player.component';

describe('EditPlayerComponent', () => {
  let component: EditPlayerComponent;
  let fixture: ComponentFixture<EditPlayerComponent>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [ EditPlayerComponent ]
    })
    .compileComponents();

    fixture = TestBed.createComponent(EditPlayerComponent);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });

  it('should create', () => {
    expect(component).toBeTruthy();
  });
});

// edit-player.component.ts down below
import { Component, OnInit } from '@angular/core';
import { CurlingbioService } from 'src/app/curlingbio.service';

@Component({
  selector: 'app-edit-player',
  templateUrl: './edit-player.component.html',
  styleUrls: ['./edit-player.component.scss']
})
export class EditPlayerComponent implements OnInit {
  constructor(private curlingbioService: CurlingbioService) { }
  //would have private route: Activated Route in the constructor parentheses.

  //If other parts worked, I could then insert the playerId.
  //curlingbioId: string;

  ngOnInit() {
    //Below is what I would write if I was able to follow Devstackr's 5th video tutorial to help me how to set up new player
    // this.route.params.subscribe(
      //(params: Params) => {
            //this.curlingbio = curlingbio;
        //}
      //)
  }

  updatePlayers() {
    //this.curlingbioService.updatePlayers(this.curlingbioId)
    
  }

}

//Updated code from csc560a3p2new4 folder, which is in MERN4 folder along with frontend
//Alex Cayer CSC 560 Assign 3.2 Attempt 4
//Purpose of the program: To create API from CSC 560 Assign 2 that can add, delete, update, 
//and 5 chosen functions.
//Note that I did utilize parts of the code from Sudeep Timalsina's tutorial, 
//"Create your First REST API with Node.js, Express and MongoDB"
//as a guide to help build each of the steps (Timalsina, 2020).
//But, did make sure to implement some code not talked about in tutorial as well.

//index4.js down below

//Import Express
let express = require('express');

//Allows application to start
let app = express();

//Import CORS down below. Will be in GREEN until ready to install.
var cors = require('cors');

//Chooses specific port to use
var port = process.env.PORT || 8080;

//Welcome message for testing purposes
app.get('/', (req, res) => res.send('Welcome to Express'));

//Helps start the application at port number
app.listen(port, function() {
    console.log("Running csc560a3p2 on Port" + port)
})

//Helping to look over the parts regarding application/json. 
//This was referenced to help adding new data as noted from user Rafael Sanchez in Timalsina's article 
//(Timalsina, 2020).
app.use(express.json())
app.use(express.urlencoded({ extended: true})) //"parsing application/x-www-form-urlencoded" (Timalsina, 2020).

//Utilizing cors module. In GREEN text until ready to use.
app.use(cors());

//Import routes itself
let apiRoutes = require("./routes")
//Then utilizes the routes above for application
app.use('/api', apiRoutes)

//import body parser
let bodyParser = require('body-parser');
//imports the mongoose package
let mongoose = require('mongoose');

//sets up bodyparser to deal with "post requests" (Timalsina, 2020)
app.use(bodyParser.urlencoded ({
    extended: true
}));

//links up with mongoose. Utilized 127.0.0.1 due to not being able to connect to mongodb with localhost.
//Found this out when viewing Database Administrators' post called "Unable to use Mongodb in NodeJS", which
//suggests to use 127.0.0.1 over localhost (Database Administrators, 2022).
const dbPath = 'mongodb://127.0.0.1/csc560a3p2new4';
const options = {useNewUrlParser: true, useUnifiedTopology: true}
const mongo = mongoose.connect(dbPath, options);

mongo.then(() => {
    console.log('connected');
}, error => {
    console.log(error, 'error');
})


//curlingbioModel.js down below
//Helps make the model in the first place.

var mongoose = require('mongoose');

//schema itself down below
var curlingbioSchema = mongoose.Schema({
    name: {
        type: String,
        required: true
    },
    age: {
        type: Number,
        required: true
    },
    gender: {
        type: String,
        required: true
    },
    position: {
        type: String,
        required: true
    },
    teamname: {
        type: String,
        required: true
    },
    totalthrowsthatstayinplay: {
        type: Number,
        required: true
    },
    totaleliminatethrows: {
        type: Number,
        required: true
    },
    sweepturnspergame: {
        type: Number,
        required: true
    },
    teamwins: {
        type: Number,
        required: true
    },
    yearsofexperience: {
        type: Number,
        required: true
    }
});

//Sends out the Curlingbio Model
var Curlingbio = module.exports = mongoose.model('curlingbio', curlingbioSchema);

module.exports.get = function (callback, limit) {
    Curlingbio.find(callback).limit(limit);
}

//routes.js of csc560a3p2 version 4
//Helps test API itself

//sets up the express router
let router = require('express').Router();

//set default API response
router.get('/', function (req, res) {
    res.json({
        status: 'API Works',
        message: 'Welcome to Alex C CSC560A3P2 API'
    })
})

//Utilizes the Bio Controller to help with routing
var curlingbioController = require('./curlingbioController');

//Curlingbio routes
router.route('/curlingbio')
    .get(curlingbioController.index)
    .post(curlingbioController.add);

router.route('/curlingbio/:curlingbio_id')
    .get(curlingbioController.view)
    .patch(curlingbioController.update)
    .put(curlingbioController.update)
    .delete(curlingbioController.delete);


//Attempted routes down below that resulted in something like "Curlingbio.findByTeamname is not a function".
//Thinking it is a route error after talking with Dr. Litman on 2/15/2023, which had the same thought (Litman, 2023).
//router.route('/curlingbio/:curlingbio_teamname')
    //.get(curlingbioController.view);
//router.route('/curlingbio/:curlingbio_gender')
    //.get(curlingbioController.view);
//router.route('/curlingbio/:curlingbio_yearsofexperience')
    //.get(curlingbioController.view);
//router.route('/curlingbio/:curlingbio_age')
    //.get(curlingbioController.view);
//router.route('/curlingbio/:curlingbio_totalthrowsthatstayinplay')
    //.get(curlingbioController.view);

//Export API routes
module.exports = router;

//curlingbioController.js
//Purpose is to handle many different requests.

//Utilizes Bio Model or in this case, it is "imported" (Timalsina, 2020)
Curlingbio = require('./curlingbioModel');

//Index portion below
exports.index = function (req, res) {
    Curlingbio.get(function (err, curlingbio) {
        if (err)
            res.json({
                status: "error",
                message: err
            });
        res.json({
            status: "success",
            message: "Got Curlingbio Successfully!",
            data: curlingbio
        });
    });
};

//For creating new Curling bio on person
exports.add = function(req, res) {
    var curlingbio = new Curlingbio();
    curlingbio.name = req.body.name? req.body.name: curlingbio.name;
    curlingbio.age = req.body.age;
    curlingbio.gender = req.body.gender;
    curlingbio.position = req.body.position;
    curlingbio.teamname = req.body.teamname;
    curlingbio.totalthrowsthatstayinplay = req.body.totalthrowsthatstayinplay;
    curlingbio.totaleliminatethrows = req.body.totaleliminatethrows;
    curlingbio.sweepturnspergame = req.body.sweepturnspergame;
    curlingbio.teamwins = req.body.teamwins;
    curlingbio.yearsofexperience = req.body.yearsofexperience;

    //Saves the new bio and then checks to see if any error happened
    curlingbio.save(function (err) {
        if (err)
            res.json(err);
        res.json({
            message: "New Curlingbio on Player Added!",
            data: curlingbio
        });
    });
};

//View Bio regarding Id, which can help identify specific user.
//Example is Katie Brief, which has the lowest totalthrowsthatstayinplay of 3 (performed in query 1 of 
// CSC 560 Assignment 2 on the CurlingteamsUpdated database. This query was taken as a screenshot for proof
//for that assignment).
exports.view = function (req, res) {
    Curlingbio.findById(req.params.curlingbio_id, function (err, curlingbio) {
        if (err)
            res.send(err);
        res.json({
            message: 'Curlingbio Details on Player(s)',
            data: curlingbio
        });
    });
};

//Update Bio
exports.update = function (req, res) {
    Curlingbio.findById(req.params.curlingbio_id, function (err, curlingbio) {
        if (err)
            res.send(err);
        curlingbio.name = req.body.name ? req.body.name : curlingbio.name;
        curlingbio.age = req.body.age;
        curlingbio.gender = req.body.gender;
        curlingbio.position = req.body.position;
        curlingbio.teamname = req.body.teamname;
        curlingbio.totalthrowsthatstayinplay = req.body.totalthrowsthatstayinplay;
        curlingbio.totaleliminatethrows = req.body.totaleliminatethrows;
        curlingbio.sweepturnspergame = req.body.sweepturnspergame;
        curlingbio.teamwins = req.body.teamwins;
        curlingbio.yearsofexperience = req.body.yearsofexperience;

        //save Curlingbio player changes and checks if any errors occured.
        curlingbio.save(function (err) {
            if (err)
                res.json(err)
            res.json({
                message: "Curlingbio of Player Updated Successfully",
                data: curlingbio
            });
        });
    });
};

//Delete Curlingbio of specific player
exports.delete = function (req, res) {
    Curlingbio.deleteOne({
        _id: req.params.curlingbio_id
    }, function (err, contact) {
        if (err)
            res.send(err)
        res.json({
            status: "success",
            message: 'Curlingbio of Player Deleted'
        })
    })
}

//Attempt of finding lowest throw that stay in play.
//exports.view = function(req, res) {
    //Curlingbio.findByTotalthrowsthatstayinplay(req.params.curlingbio_totalthrowsthatstayinplay, function(err, curlingbio) {
        //if (err)
            //res.send(err);
        //res.json({
            //message: "Found Curlinbio Player that has a certain amount of total throws that stay in play",
            //data: curlingbio
        //})
    //})
//}

//View Curlingbio of Players on specific teams based on teamname.
//exports.view = function (req, res) {
    //Curlingbio.findByTeamname(req.params.curlingbio_teamname, function (err, curlingbio) {
        //if (err)
            //res.send(err);
        //res.json({
            //message: 'Curlingbio Team Player Details',
            //data: curlingbio
        //});
    //});
//};

//View Curlingbio of Players who have specific gender or in this case, male or female.
//exports.view = function (req, res) {
    //Curlingbio.findByGender(req.params.curlingbio_gender, function (err, curlingbio) {
        //if (err)
            //res.send(err);
        //res.json({
            //message: 'Curlingbio Team Player(s) who are this Gender Details',
            //data: curlingbio
        //})
    //})
//}

//Sorts players by years of experience in reverse order or in this case descending from most years to lowest.
//query can be used to order by specific query parameters or in this case, try to order from ascending to descending.
//exports.view = function (req, res) {
    //Curlingbio.sortByYearsofexperience(req.query.curlingbio_yearsofexperience, function (err, curlingbio) {
        //if (err)
            //res.send(err);
        //res.json({
            //message: 'Curlingbio Team Player(s) sorted by yearsofexperience',
            //data: curlingbio

        //})
    //})


//}

//Sorts players by age. Trying to sort players who are greater than 30 years old.
//exports.view = function(req, res) {
    //Curlingbio.filterByAge(req.query.curlingbio_age, function(err, curlingbio) {
        //if (err)
            //res.send(err);
        //res.json({
            //message: 'Curlingbio Team Player(s) filtered by age',
            //data: curlingbio

        //})
    //})
//}

//package.json file down below

{
  "name": "csc560a3p2new4",
  "version": "1.0.0",
  "description": "Creating API for CSC 560 assign 2",
  "main": "index4.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "restapi"
  ],
  "author": "Alex Cayer",
  "license": "ISC",
  "dependencies": {
    "body-parser": "^1.20.1",
    "cors": "^2.8.5",
    "express": "^4.18.2",
    "expression": "^0.0.1",
    "mongoose": "^6.9.1",
    "routes": "^2.1.0"
  }
}


//End of code here

//References
//Bulma. (n.d.). Dropdown. Retrieved March 4, 2023, from https://bulma.io/documentation/components/dropdown/
//Referred to this web page on documentation in regards to dropdown. Also, was discussed in Devstackr's tutorial video series on task manger in Angular.
//Bulma. (n.d.). Form controls. Retrieved March 4, 2023, from https://bulma.io/documentation/form/general/
//Utilized this web page from Bulma since I utilized the many styles and templates from this folder for assignments 4.2-4.3.
//Computer Hope. (n.d.). HTML color codes and names. Retrieved March 4, 2023, from https://www.computerhope.com/htmcolor.htm
//Referred to this site briefly when it came to thinking of which color codes I wanted to utilize. In the end, I didn't use them but may be a useful source down the //line.
//Devstackr. (2019, April). Build a Task Manager Application From Scratch (MEAN Stack). YouTube. Retrieved March 4, 2023, from https://www.youtube.com/playlist?list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd
//For assignment 4.2 and most likely, assignment 4.3, I referred to videos 1 to 6 and then video 14 to try to build my Angular application. Utilized own words but //referred to these videos as guide as how to set up the various pages.
//Devstackr. (2019, April). Task-manager-mean-stack. GitHub. Retrieved March 4, 2023, from https://github.com/Devstackr/task-manager-mean-stack
//Referred to this web page to check to make sure I was coding in a similar way Devstackr formed each of the pages within Angular.
//Devstackr. (2019, April 9). Creating the UI- [2] Build a Task manager w/Angular, NodeJS, and MongoDB [Video]. YouTube. https://www.youtube.com/watch?v=BO67e3QU9dU&list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd&index=3
//Devstackr. (2019, April 9). Project Demo & Introduction- [1] Build a Task manager w/Angular, NodeJS and MongoDB [Video]. YouTube. https://www.youtube.com/watch?v=V-CeWkz1MNQ&list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd&index=2
//Devstackr. (2019, April 10). Building the Api | NodeJS, Express and MongoDB- [3] Build a Task Manager w/MEAN Stack [Video]. YouTube. https://www.youtube.com/watch?v=P3R-8jj3S7U&list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd&index=3
//Devstackr. (2019, April 10). Connecting Angular Frontend to the API- [4] Build a Task Manager w/Angular, NodeJS and MongoDB [Video]. YouTube. https://www.youtube.com/watch?v=185uAxYz1dU&list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd&index=4
//Devstackr. (2019, April 10). Creating Lists and Displaying in Sidebar- [5] Build a Task Manager w/Angular, NodeJS and MongoDB [Video]. YouTube. https://www.youtube.com/watch?v=aOkAx1jZokc&list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd&index=5
//Devstackr. (2019, April 10). New Task Button (FAB)- [6] Build a Task Manager w/Angular, NodeJS and MongoDB [Video]. YouTube. https://www.youtube.com/watch?v=7YK4pJZG0oA&list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd&index=6
//Devstackr. (2019, April 13). Updating and Deleting Lists & Tasks- [14] Build a Task Manager w/Angular, NodeJS, and MongoDB [Video]. YouTube. https://www.youtube.com/watch?v=XM-1lNLuJjg&list=PLIjdNHWULhPSZFDzQU6AnbVQNNo1NTRpd&index=16
//Litman, D. (2023, March 2). [Personal interview by A. Cayer].
//Meeting with Dr. Litman to confirm some questions regarding unit 4. After meeting with him, I feel better regarding the current assignments.

