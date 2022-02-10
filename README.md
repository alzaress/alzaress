
string pass = "password", salt = "", hash = "", pass2 = "", hash2 = "";
bool check = false;

Console.WriteLine("Test bcrypt!");
Console.WriteLine("Generate salt");

salt = BCrypt.Net.BCrypt.GenerateSalt(SaltRevision.Revision2B);

Console.WriteLine("Password = {0}, salt = {1}", pass, salt);
Console.WriteLine("Generate hash = pass + salt");

hash = BCrypt.Net.BCrypt.HashPassword(pass, salt);

Console.WriteLine("Hash = {0}", hash);

Console.WriteLine("Check verification pass");
Console.Write("Input new pass - ");
pass2 = Console.ReadLine();

hash2 = BCrypt.Net.BCrypt.HashPassword(pass2, salt);
Console.WriteLine("Salt = {0}", salt);
Console.WriteLine("Hash2 = {0}", hash2);

check = hash2 == hash ;
Console.WriteLine("Veritification end");
Console.WriteLine("Result - {0}", check);
