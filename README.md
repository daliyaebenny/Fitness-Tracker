# Fitness Tracker

Track your workouts with Fitness Tracker. The app will keep track of every exercise in your workout. The app dashboard will display weekly summary graphs of all workouts done in a week.

## Table of Contents

* [Installation](#installation)
* [Usage](#usage)
    * [Screenshots](#screenshots)
    * [Snippets](#snippets)
* [Credits](#credits)
* [Links](#links)

## Installation

1. Clone repository. 
2. Check in routes/api-routes and comment in block of code if you want the database to be prepopulated with dummy values
3. npm install
4. node server.js

## Usage

### Screeshots

1. Homepage displaying last workout

![Site](public/assets/)

2. Creating Workouts

![Site](public/assets/live.gif)


3. Last Week's Summary

![Site](public/assets)

### Snippets


1. Adding to an array type

```javascript

    // add exercise
    app.put("/api/workouts/:id", (req, res) => {

        db.Workout.findOneAndUpdate(
            { _id: req.params.id },
            {
                $inc: { totalDuration: req.body.duration },
                $push: { exercises: req.body }
            },
            { new: true }).then(dbWorkout => {
                res.json(dbWorkout);
            }).catch(err => {
                res.json(err);
            });

    });
    
```
* This function will add an exercise to the array of exercises that belong to the workout with the given id. Here we will locate the workout with the given ID and update its fields. We will increase the total duration of the workout by the duration of the exercise being inserted. We will push the exercise to the array of exercises.


## Credits

### Author

 - Daliya Benny

### Technology

HTML,CSS,Javascript,Bootstrap,NodeJS,Express,MongoDB

   
## Links    
 - [Github](https://github.com/daliyaebenny/Fitness-Tracker.git/)    
 - [Live](https://infinite-caverns-58397.herokuapp.com/)

  

