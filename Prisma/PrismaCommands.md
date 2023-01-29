## How to select all table items:

```
prisma.[TABLE].findMany();
```

_____________________________________________________________________________________________________________

## How to insert objects inside a Prisma table:

```
prisma.[TABLE].create({
  data: job
});
```

_____________________________________________________________________________________________________________

## In this function, if the data exists, it makes an update, if it does not exist, it inserts the data:

```
prisma.[TABLE].upsert(
  where { 
    id : job.id || 0,       
    },
 create: job,
 update: job                // Or if you wanted to update only some of the job data, do it like this -->
 {
  title: job.title
 }

);
```

_____________________________________________________________________________________________________________

## How to select all table items:

```
prisma.[TABLE].findMany();
```

_____________________________________________________________________________________________________________
