# Migration `20200806000631-fix-something`

This migration has been generated by ChauLe19 at 8/6/2020, 12:06:31 AM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql

```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200805235727-init..20200806000631-fix-something
--- datamodel.dml
+++ datamodel.dml
@@ -3,9 +3,9 @@
 }
 datasource db {
   provider = "sqlite"
-  url = "***"
+  url = "***"
 }
 model User {
   id                                        Int           @default(autoincrement()) @id
@@ -35,8 +35,8 @@
   productId                          Int
   price                              Float
   sellerEmail                        String
   buyerEmail                         String
-  User_Transaction_buyerEmailToUser  User     @relation("BuyTransaction", fields: [buyerEmail], references: [email])
-  Book                               Book     @relation(fields: [productId], references: [id])
-  User_Transaction_sellerEmailToUser User     @relation("SellTransaction", fields: [sellerEmail], references: [email])
+  buyer  User     @relation("BuyTransaction", fields: [buyerEmail], references: [email])
+  product                               Book     @relation(fields: [productId], references: [id])
+  seller User     @relation("SellTransaction", fields: [sellerEmail], references: [email])
 }
```


