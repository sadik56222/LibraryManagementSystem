#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct books_info
{
    int id;
    char name[100];
    char author[100];
    int quantity;
};

void main_menu();
void admin_menu();
void user_menu();
void about_group_member();
void password();
void add_books();
void view_books();
void search_books();
void book_delete();
void number_of_book();
void borrow_book();
void deposit_book();
void books_list();
void search_books_u();

FILE *books_info, *books_info2;

int main()
{
    main_menu();
    return 0;
}

void main_menu()
{
    int press1;
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|          Library Management System          |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\t\t\t\t1.Admin Mode\n");
    printf("\n\n\t\t\t\t2.User Mode\n");
    printf("\n\n\t\t\t\t3.About Group Member\n");
    printf("\t\t\t\t***********************************************\n");
    printf("\t\t\t\tEnter what you want : ");
    scanf("%d", &press1);

    if (press1 == 1)
    {
        password();
        admin_menu();
    }
    else if (press1 == 2)
    {
        user_menu();
    }
    else if (press1 == 3)
    {
        about_group_member();
    }
    else
    {
        printf("\n\n\t\t\t\tWrong input\n");
        printf("\n\n\t\t\t\tPress any key to go MAIN MENU\n");
        fflush(stdin);
        getchar();
        main_menu();
    }
}

void about_group_member()
{
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t\t|          Library Management System          |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\t\t\t\tName : Nahidul Islam Forhad\n\nID : 0242310005101246\n\nSection : 64_C\n\nDept. of Computer Science & Enginerring\n\nDaffodil International University\n");
    printf("\n\n\t\t\t\tName : Hanjala Habib Sadik\n\nID : 0242310005101010\n\nSection : 64_C\n\nDept. of Computer Science & Enginerring\n\nDaffodil International University\n");
    printf("\n\n\t\t\t\tName : Susmita Akand Tama\n\nID : 0242310005101478\n\nSection : 64_C\n\nDept. of Computer Science & Enginerring\n\nDaffodil International University\n");
    printf("\n\n\t\t\t\tName : Md. Amir Hossain\n\nID : 0242310005101674\n\nSection : 64_C\n\nDept. of Computer Science & Enginerring\n\nDaffodil International University\n");
    printf("\t\t\t\t**********************WELCOME***********************\n");
    printf("\n\n\t\t\t\tPress anykey to get back....");
    fflush(stdin);
    getchar();
    main_menu();
}

void password()
{
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|          Library Management System          |\n");
    printf("\t\t\t\t|*********************************************|\n");
    char given_password[100] = "024";
    char give_password[100];
    printf("\n\n\t\t\t\tENTER PASSWORD : ");
    scanf("%s", give_password);
    int match_password = strcmp(give_password, given_password);
    if (match_password == 0)
    {
        printf("\n\t\t\t\tCorrect password :)\n");
        admin_menu();
    }
    else
    {
        int n;
        printf("\n\t\t\t\tWrong Password :(\n");
        printf("\n\t\t\t\tPress 0 to get back or write password to access : ");
        scanf("%d", &n);
        if (n == 0)
        {
            main_menu();
        }
        else
        {
            password();
        }
        fflush(stdin);
        getchar();
    }
    fflush(stdin);
    getchar();
}

void admin_menu()
{
    int press2;
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|              Menu For Admin                 |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\t\t\t\t1.Add Books\n");
    printf("\n\n\t\t\t\t2.View Books\n");
    printf("\n\n\t\t\t\t3.Search Books\n");
    printf("\n\n\t\t\t\t4.Number of Books\n");
    printf("\n\n\t\t\t\t5.Books Delete\n");
    printf("\n\n\t\t\t\t6.Back\n");
    printf("\n\n\t\t\t\tEnter any number:");
    scanf("%d", &press2);
    if (press2 == 1)
    {
        add_books();
    }
    else if (press2 == 2)
    {
        view_books();
    }
    else if (press2 == 3)
    {
        search_books();
    }
    else if (press2 == 4)
    {
        number_of_book();
    }
    else if (press2 == 5)
    {
        book_delete();
    }
    else if (press2 == 6)
    {
        main_menu();
    }
    else
    {
        printf("\n\n\t\t\t\tWrong input\n");
        printf("\n\n\t\t\t\tPress any key to go ADMIN MENU\n");
        fflush(stdin);
        getchar();
        admin_menu();
    }
}

void user_menu()
{
    int press3;
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|              Menu For User                  |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\t\t\t\t1.Search Books\n");
    printf("\n\n\t\t\t\t2.Books List\n");
    printf("\n\n\t\t\t\t3.Borrow Books\n");
    printf("\n\n\t\t\t\t4.Deposit Books\n");
    printf("\n\n\t\t\t\t5.Back\n");
    printf("\n\n\t\t\t\tEnter any number:");
    scanf("%d", &press3);
    if (press3 == 1)
    {
        search_books_u();
    }
    else if (press3 == 2)
    {
        books_list();
    }
    else if (press3 == 3)
    {
        borrow_book();
    }
    else if (press3 == 4)
    {
        deposit_book();
    }
    else if (press3 == 5)
    {
        main_menu();
    }
    else
    {
        printf("\n\n\t\t\t\tWrong input\n");
        printf("\n\n\t\t\t\tPress any key to go USER MENU\n");
        fflush(stdin);
        getchar();
        user_menu();
    }
}

void add_books()
{
    system("cls");
    int id, count = 0;
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|                  ADD BOOKS                  |\n");
    printf("\t\t\t\t|*********************************************|\n");

    struct books_info book;
    books_info = fopen("books.txt", "ab+");

    if (books_info == NULL)
    {
        printf("Failed to open file.\n");
        return;
    }

    printf("\n\n\t\t\t\tEnter Books ID : ");
    scanf("%d", &id);
    rewind(books_info);

    while (fread(&book, sizeof(book), 1, books_info) == 1)
    {
        if (id == book.id)
        {
            printf("\n\n\t\t\tThis book is already added in the library.\n");
            count = 1;
            break; // Exit the loop if the book is already added
        }
    }

    if (count == 1)
    {
        fflush(stdin);
        getchar();
        fclose(books_info);
        admin_menu();
        return;
    }

    book.id = id;

    printf("\n\n\t\t\tEnter Books Name : ");
    fflush(stdin);
    // fgets(book.name, sizeof(book.name), stdin);
    gets(book.name);
    //scanf("%[^\n]s", book.name);

    printf("\n\n\t\t\tEnter Books Author Name : ");
    fflush(stdin);
    // fgets(book.author, sizeof(book.author), stdin);
    gets(book.author);
    //scanf("%[^\n]s", book.author);

    printf("\n\n\t\t\tEnter Books Quantity : ");
    scanf("%d", &book.quantity);

    fseek(books_info, 0, SEEK_END);
    fwrite(&book, sizeof(book), 1, books_info);

    fclose(books_info);

    printf("\n\n\t\t\tBook added successfully.\n");
    
    printf("Enter Any Key to go MENU FOR ADMIN...");
    fflush(stdin);
    getchar();
    admin_menu();
}

void view_books()
{
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|                 VIEW BOOKS                  |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\tID\t\t\tName\t\t\tAuthor\t\t\tQuantity\n\n");

    struct books_info book; // Create a variable to store book information

    books_info = fopen("books.txt", "rb"); // Open the file in read mode

    if (books_info == NULL)
    {
        printf("Failed to open file.\n");
        return;
    }

    while (fread(&book, sizeof(book), 1, books_info) == 1)
    {
        printf("\t%d", book.id);
        printf("\t\t\t%s", book.name);
        printf("\t\t%s", book.author);
        printf("\t\t\t%d", book.quantity);
        printf("\n");
    }


    printf("Enter Any Key to go MENU FOR ADMIN...");
    fflush(stdin);
    getchar();

    fclose(books_info);

    admin_menu();
}

void search_books()
{
    int id, count = 0;
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|               SEARCH BOOKS                  |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\t\t\tEnter Books ID : ");
    scanf("%d", &id);
    struct books_info book;
    books_info = fopen("books.txt", "rb");
    while (fread(&book, sizeof(book), 1, books_info) == 1)
    {
        if (id == book.id)
        {
            printf("\n\n\t\t\tThis book is available in the library.\n");
            printf("\n\n\tID\t\t\tName\t\t\tAuthor\t\t\tQuantity\n\n");
            printf("\t%d", book.id);
            printf("\t\t\t%s", book.name);
            printf("\t\t%s", book.author);
            printf("\t\t\t%d", book.quantity);
            printf("\n");
            count++;
        }
    }
    if (count == 0)
    {
        printf("\n\n\t\t\tThis book is not available in the library.\n");
    }
    printf("\n\nEnter Any Key to go MENU FOR ADMIN...");
    fclose(books_info);
    fflush(stdin);
    getchar();
    admin_menu();
}

void book_delete()
{
    int id, count = 0;
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|               BOOKS DELETE                  |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\t\t\tEnter ID for delete books : ");
    scanf("%d", &id);
    struct books_info book;
    books_info = fopen("books.txt", "rb");
    rewind(books_info);
    while (fread(&book, sizeof(book), 1, books_info) == 1)
    {
        if (id == book.id)
        {
            printf("\n\n\t\t\tThis book is available in the library.\n\n\n");
            printf("\t%s", book.name);
            count++;
        }
    }
    if (count == 0)
    {
        printf("\n\n\t\t\tBook is not Availble");
    }
    else
    {
        books_info2 = fopen("text.txt", "wb");
        rewind(books_info);
        while (fread(&book, sizeof(book), 1, books_info) == 1)
        {
            if (id != book.id)
            {
                fseek(books_info2, ftell(books_info2) - sizeof(book), 0);
                fwrite(&book, sizeof(book), 1, books_info2);
            }
        }
        fclose(books_info);
        fclose(books_info2);
        remove("books.txt");
        rename("text.txt", "books.txt");
        books_info = fopen("books.txt", "rb");
    }
    printf("Enter Any Key to go MENU FOR ADMIN...");
    fflush(stdin);
    getchar();
    admin_menu();
}


void number_of_book(){

   

    system("cls");
    int count = 0;
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|                 NUMBER OF BOOKS             |\n");
    printf("\t\t\t\t|*********************************************|\n");

    struct books_info book; // Create a variable to store book information

    books_info = fopen("books.txt", "rb"); // Open the file in read mode

    if (books_info == NULL)
    {
        printf("Failed to open file.\n");
        return;
    }

    while (fread(&book, sizeof(book), 1, books_info) == 1)
    {
        count += book.quantity;
    }

    printf("\n\n\t\t\tNumber Of Books : %d\n", count);

    printf("Enter Any Key to go MENU FOR ADMIN...");
    fflush(stdin);
    getchar();

    fclose(books_info);

    admin_menu();
}

//user start


void borrow_book() {
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|               BORROW BOOKS                  |\n");
    printf("\t\t\t\t|*********************************************|\n");

    struct books_info book;
    char search_name[100];
    int search_id;

    printf("\n\nEnter the name of the book: ");
    fflush(stdin);
    //fgets(search_name, sizeof(search_name), stdin);
    gets(search_name);

    printf("Enter the ID of the book: ");
    fflush(stdin);
    scanf("%d", &search_id);

    int found = 0;
    books_info = fopen("books.txt", "rb+");
    if (books_info == NULL) {
        printf("Failed to open file.\n");
        return;
    }

    while (fread(&book, sizeof(book), 1, books_info) == 1) {
        if (strcmp(book.name, search_name) == 0 && book.id == search_id) {
            if (book.quantity > 0) {
                book.quantity--;
                fseek(books_info, -sizeof(book), SEEK_CUR); // move file pointer back
                fwrite(&book, sizeof(book), 1, books_info); // update the book quantity
                found = 1;
                break;
            } else {
                printf("Book is not available for borrowing.\n");
                found = 1;
                break;
            }
        }
    }

    if (found) {
        printf("Book borrowed successfully.\n");
    } else {
        printf("Book not found in the library.\n");
    }

    printf("\n\nEnter Any Key to go back to MENU FOR USER...");
    fclose(books_info);
    fflush(stdin);
    getchar();
    user_menu();
}



void deposit_book() {
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|               DEPOSIT BOOKS                  |\n");
    printf("\t\t\t\t|*********************************************|\n");

    struct books_info book;
    char search_name[100];
    int search_id;

    printf("\n\nEnter the name of the book: ");
    fflush(stdin);
    //fgets(search_name, sizeof(search_name), stdin);
    gets(search_name);

    printf("Enter the ID of the book: ");
    fflush(stdin);
    scanf("%d", &search_id);

    int found = 0;
    books_info = fopen("books.txt", "rb+");
    if (books_info == NULL) {
        printf("Failed to open file.\n");
        return;
    }

    while (fread(&book, sizeof(book), 1, books_info) == 1) {
        if (strcmp(book.name, search_name) == 0 && book.id == search_id) {
                book.quantity++;
                fseek(books_info, -sizeof(book), SEEK_CUR); // move file pointer back
                fwrite(&book, sizeof(book), 1, books_info); // update the book quantity
                found = 1;
                break;
        }
    }

    if (found) {
        printf("Book deposited successfully.\n");
    } else {
        printf("Book not found in the library.\n");
    }

    printf("\n\nEnter Any Key to go back to MENU FOR USER...");
    fclose(books_info);
    fflush(stdin);
    getchar();
    user_menu();
}



void books_list()
{
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|                 BOOKS LIST                  |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\tID\t\t\tName\t\t\tAuthor\t\t\tQuantity\n\n");

    struct books_info book; // Create a variable to store book information

    books_info = fopen("books.txt", "rb"); // Open the file in read mode

    if (books_info == NULL)
    {
        printf("Failed to open file.\n");
        return;
    }

    while (fread(&book, sizeof(book), 1, books_info) == 1)
    {
        printf("\t%d", book.id);
        printf("\t\t\t%s", book.name);
        printf("\t\t%s", book.author);
        printf("\t\t\t%d", book.quantity);
        printf("\n");
    }


    printf("Enter Any Key to go MENU FOR ADMIN...");
    fflush(stdin);
    getchar();

    fclose(books_info);

    user_menu();
}


void search_books_u()
{
    int id, count = 0;
    system("cls");
    printf("\n\n\t\t\t\t|*********************************************|\n");
    printf("\t\t\t\t|               SEARCH BOOKS                  |\n");
    printf("\t\t\t\t|*********************************************|\n");
    printf("\n\n\t\t\tEnter Books ID : ");
    scanf("%d", &id);
    struct books_info book;
    books_info = fopen("books.txt", "rb");
    while (fread(&book, sizeof(book), 1, books_info) == 1)
    {
        if (id == book.id)
        {
            printf("\n\n\t\t\tThis book is available in the library.\n");
            printf("\n\n\tID\t\t\tName\t\t\tAuthor\t\t\tQuantity\n\n");
            printf("\t%d", book.id);
            printf("\t\t\t%s", book.name);
            printf("\t\t%s", book.author);
            printf("\t\t\t%d", book.quantity);
            printf("\n");
            count++;
        }
    }
    if (count == 0)
    {
        printf("\n\n\t\t\tThis book is not available in the library.\n");
    }
    printf("\n\nEnter Any Key to go MENU FOR ADMIN...");
    fclose(books_info);
    fflush(stdin);
    getchar();
    user_menu();
}
