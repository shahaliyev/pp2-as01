# Programming Principles II - Assignment 1

## Object Oriented Programming

You goal is to implement a java program to store and manage information about your favorite movies/tv shows.

While implementing, you should strictly follow the OOP principles, have your classes separated, apply method/constructor overloading whenever necessary, choose reasonable modifiers and data types, as well as apply abstraction, encapsulation, polymorphism, and inheritence.

`MotionPicture class` should be an `abstract` class with following members:
- title
- year
- runningTime

You should notify the user if `year` and `runningTime` are impossible numbers. It means that year should be between _1895 and 2023_, that is between the year of the first movie demonstrated by Lumière brothers and the current year. Running time cannot be a negative number.

`Movie class` should inherit from `MotionPicture` and have following members:
- director
- screenWriters
- starring

`TVShow class` should inherit from `MotionPicture` and have following members:
- creator
- numberOfEpisodes
- episodes

Here `episodes` should be an array of movies (`Movie[]`). It means that `TVShow class` should be able to accept an array of movies in its constructor, and by the length of the array, extract a value for `numberOfEpisodes`. You will soon see an example below.

All of your classes should have getters and setters, as well as `toString()` method. You may enforce overriding of `toString()` method in child classes by the abstract method in `MotionPicture` as follows:

```java
@Override
    public abstract String toString();
```

You should overload constructors as well. Calling constructor with no arguments as follows,

```java
Movie movie1 = new Movie();
```
should put data about your favorite movie into `movie1` object.


## Outcome
What is below should give a rough illustration on how your program should work. Your program should **NOT** work **exactly** as below, but it should be similar.
In `Main.java` your program should function approximately like this:

```java
public static void main(String[] args) {
    // Puts data about your favorite movie into movie1 object
    Movie movie1 = new Movie();

    // If the constructor accepts title, director, screenWriters, starring, year, runningTime
    Movie movie2 = new Movie("Tütək səsi", "Rasim Ocaqov", new String[] {"Isa Hüseynov"}, new String[] {"Akif Məhərrəmov", "Mihai Volontir", "Məmmədrza Şeyxzamanov", "Zemfira Sadıqova"}, 1975, 82);

    Movie movie3 = new Movie("Insert your another favorite movie info");

    // If the constructor accepts title, year, creator, episodes
    TVShow show1 = new TVShow("Untitled_Show", 2023, "Creator_of_show", new Movie[] {movie1, movie2, movie3});

// Method below will return 3, as we passed three movies to the Movie[] array above.
    System.out.println(show1.getNumberOfEpisodes());
        
}
```

Here `System.out.println(show1)` should call `toString()` method of `TVShow` and return important information about the show, for example:
- title
- runningTime
- number of episodes
- episodes (which in their own turn will call `toString()` method of `Movie`)


## Grading criteria

**Your code (`Main.java`) should run. In case of errors when running grade will be zero.**

Possible points are shown inside `[]`.

### `MotionPicture.java` [20]

Members are defined correctly, logical data types and modifiers are chosen, `toString()` method is overridden.

### `Movie.java` [30]

Extends `MotionPicture`.

Members are defined correctly, logical data types and modifiers are chosen, `toString()` method is overridden.

Overloads its constructor. Default constructor with no arguments should return data about your favorite movie:

```java
Movie myFavMovie = new Movie();
System.out.println(myFavMovie);
// Your favorite movie details are printed
```

### `TVShow.java` [30]

Extends `MotionPicture`. 

Members are defined correctly, logical data types and modifiers are chosen, `toString()` method is overridden.

Overloads its constructor. Array of movies can be passed to its constructor (see the example above).

### `Main.java` [15]

Illustrates how all these classes work together. See the example above.

It should also have the following method:

```java
public static int getTotalRunningTime(MotionPicture[] mps){
    // code logic
}
```

which will get a `MotionPicture` array as its input and sum the running time of its elements. Note that, as a parent class, `MotionPicture[]` can accept both `Movie` and `TVShow` objects as its argument:

```java
    MotionPicture mps[] = new MotionPicture[]{show1, movie1, movie2};
        
    System.out.println(getTotalRunningTime(mps));
```

### Other [5]

Your code should be **tidy**. Do not put unnecessary gaps or unnecessary comments. If you think that it is meaningful to do something, do it. Make your code is understandable and easy to read. `[2]`

Make use of **git/github** properly. Make consistent and reasonable commits. Frequently used `git` commands were as follows:

```shell
git status
git add .
git commit -m "your message"
git push
```

`[2]`

Have a `README.md` file explaining your code. **Markdown language** is easy to learn is powerful. See the [MarkDown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) and test your code [here](https://dillinger.io/).

`[1]`

*On blackboard, put the link to your repository when submitting the assignment.*

















