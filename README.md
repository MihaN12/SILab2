# Втора лабораториска вежба по Софтверско инженерство
# Михаела Николовска 183014
 Група на код: 3
Control Flow Graph


public boolean function (User user, List<String> allUsers) { //node 1
        String specialCharacters="!#$%&'()*+,-./:;<=>?@[]^_`{|}"; //node 2
        if (user==null) { //node 3
            throw new RuntimeException("The user is not instantiated"); //node 4
        }
        if (user.getUsername()==null || user.getPassword()==null) //node 5
            throw new RuntimeException("The user is missing some mandatory information"); //node 6
        String password = user.getPassword();
        String passwordLower = password.toLowerCase(); //node 7
        if (passwordLower.contains(user.getUsername().toLowerCase())) { //node 8
            return false; // node 9
        }
        else if (passwordLower.length()<8) //node 10
            return false; //node 11
        else { //node 12
            boolean digit = false, upper = false, special = false; //node 13
            for (int i=0;i<password.length();i++) { //node 14 so podtocki .1 i .2 za inicijalizacija i za uslovot i .3 za loop
                if (Character.isDigit(password.charAt(i))) //node 15
                    digit = true; //node 16
                if (Character.isUpperCase(password.charAt(i))) //node 17
                    upper = true; //node 18
                if (specialCharacters.contains(String.valueOf(password.charAt(i)))) //node 19
                    special = true;//node 20
            }//node 21
            if (!digit || !upper || !special) //node 22
                return false; //node 23
        }
        return true; //node 24
    } //node 25

