# Prisma Note 1

You're occasionally using **'@map'** and **'@@map'** to mpa some field and model names to diffrent column and table _names_ in the underlying database. This is because NextAuth.js has some special _requirements_ for calling things in your database.

this prisma schema defines two models
each of which will map to table int he underlying database:
User and Pst. NOtice that threr's also a relation (one-to -many) between the two models, via the author field on post and the posts field on user.

To actually create the tables in your database, you can use the following command:
npx prisma db push

# use prisma studio interface to create a new User and Post record and connect the via their relation fields.
