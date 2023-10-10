# Programming Principles II - Assignment 1

## Object Oriented Programming

You goal is to implement a java program to store and manage information about your favorite movies/tv shows.

While implementing, you should strictly follow the OOP principles, have your classes separated, apply method/constructor overloading whenever necessary, choose reasonable modifiers and data types, as well as apply abstraction, encapsulation, polymorphism, and inheritence.

`MotionPicture class` should be an abstract class with following members:
- title
- genre
- year
- rating

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

You should overload constructors as well. Calling

```java
Movie movie1 = new Movie();
```
should put data about your favorite movie into `movie1` variable.


## Outcome
What is below should give a rough illustration on how your program should work. Your program should **NOT** work **exactly** as below, but it should be similar.
In `Main.java` your program should function approximately like this:

```java
public static void main(String[] args) {
    Movie movie1 = new Movie();
    Movie movie2 = new Movie("Tütək səsi", "Rasim Ocaqov", new String[] {"Isa Hüseynov"}, new String[] {"Akif Məhərrəmov", "Mihai Volontir", "Məmmədrza Şeyxzamanov", "Zemfira Sadıqova"}, 1975, 10, "drama");
    Movie movie3 = new Movie("Your favorite movie");

    TVShow show1 = new TVShow("Untitled_Show", 2023, "drama", "Creator_of_show", new Movie[] {movie1, movie2, movie3});
}
```

Here `System.out.println(show1)` should call `toString()` method of `TVShow` and return important information about the show, for example:
- title
- rating
- number of episodes (in this case, it should be 3, because there are three movies)
- episodes (which in their own turn will call `toString()` method of `Movie`)


## Grading criteria

**Your code (`Main.java`) should run. In case of errors when running grade will be zero.**

### `MotionPicture.java` [20]

Members are defined correctly, logical data types and access modifiers are chosen, `toString()` method is enforced.

### `Movie.java` [30]

Extends `MotionPicture`.

Members are defined correctly, logical data types and access modifiers are chosen, `toString()` method is overridden. [15]

Overloads its constructor. Default constructor with no arguments should return data about your favorite movie:

```java
Movie myFavMovie = new Movie();
System.out.println(myFavMovie);
// Your favorite movie details are printed
```

[15]

### `TVShow.java` [30]

Extends `MotionPicture`. 

Members are defined correctly, logical data types and access modifiers are chosen, `toString()` method is overridden. [15]

Overloads its constructor. Array of movies can be passed to its constructor (see the example above). [15]

### `Main.java` [20]

Illustrates how all these classes work together. See the example above.





