# oop-workshop
---
title: Digital Media System

classDiagram
    class Media{
        +String title
        +int releaseYear
        +String language
        +download()
        +viewDetails()
    }

    class Ebook{
        +String author
        +int pages
        +String isbn
    }

    class Movie{
        +String director
        +String genres
        +int duration
    }

    class Song{
        +String composer
        +String singer
        +String fileType
        +int duration
    }

    class VideoGame{
        +String publisher
        +String supportedPlatforms
    }

    class App{
        +String version
        +String publisher
        +String supportedPlatforms
        +int fileSize
    }

    class Podcast{
        +String host
        +String guests
        +int episodeNumber
        +String language
    }

    class ImageMedia{
        +String resolution
        +String fileFormat
        +int fileSize
        +String dateTaken
    }

    Media <|-- Ebook
    Media <|-- Movie
    Media <|-- Song
    Media <|-- VideoGame
    Media <|-- App
    Media <|-- Podcast
    Media <|-- ImageMedia


    %% --------- USERS ----------
    class User{
        +String name
        +int age
        +String ssn
        +identifyRole()
    }

    class Borrower{
        +listByType()
        +previewItem()
        +rateItem()
    }

    class Employee{
        +addMedia()
        +removeMedia()
    }

    class Admin{
        +manageBorrowers()
        +manageEmployees()
        +updateUserInfo()
    }

    User <|-- Borrower
    User <|-- Employee
    User <|-- Admin

    Borrower --> Media : borrows >
    User --> Media : views >
