#include <iostream>
#include <string>
using namespace std;

// Structure to store details of one item
struct Item {
    int id;         // Item ID
    string name;    // Item Name
    int quantity;   // Item Quantity
    float price;    // Item Price
};

// Inventory class to manage all items
class Inventory {
    Item items[100]; // Fixed-size array (can hold max 100 items)
    int count;       // Current number of items

public:
    Inventory() {
        count = 0; // Start with 0 items
    }

    // Add a new item
    void addItem(int id, string name, int qty, float price) {
        if (count < 100) {
            items[count].id = id;
            items[count].name = name;
            items[count].quantity = qty;
            items[count].price = price;
            count++;
            cout << "Item added successfully.\n";
        } else {
            cout << "Inventory is full! Cannot add more items.\n";
        }
    }

    // Delete an item by ID
    void removeItem(int id) {
        for (int i = 0; i < count; i++) {
            if (items[i].id == id) {
                // Shift remaining items left
                for (int j = i; j < count - 1; j++) {
                    items[j] = items[j + 1];
                }
                count--;
                cout << "Item removed successfully.\n";
                return;
            }
        }
        cout << "Item not found.\n";
    }

    // Search for an item by ID
    void searchItem(int id) {
        for (int i = 0; i < count; i++) {
            if (items[i].id == id) {
                cout << "Item Found:\n";
                cout << "ID: " << items[i].id
                     << " | Name: " << items[i].name
                     << " | Quantity: " << items[i].quantity
                     << " | Price: " << items[i].price << endl;
                return;
            }
        }
        cout << "Item not found.\n";
    }

    // Show all items
    void showAllItems() {
        if (count == 0) {
            cout << "Inventory is empty.\n";
            return;
        }
        cout << "\n--- Inventory List ---\n";
        for (int i = 0; i < count; i++) {
            cout << "ID: " << items[i].id
                 << " | Name: " << items[i].name
                 << " | Quantity: " << items[i].quantity
                 << " | Price: " << items[i].price << endl;
        }
    }
};

// Main program
int main() {
    Inventory inv;
    int choice, id, qty;
    string name;
    float price;

    do {
        // Menu
        cout << "\n===== Inventory Menu =====\n";
        cout << "1. Add Item\n";
        cout << "2. Remove Item\n";
        cout << "3. Search Item\n";
        cout << "4. Show All Items\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            cout << "Enter ID, Name, Quantity, Price: ";
            cin >> id >> name >> qty >> price;
            inv.addItem(id, name, qty, price);
            break;
        case 2:
            cout << "Enter ID to remove: ";
            cin >> id;
            inv.removeItem(id);
            break;
        case 3:
            cout << "Enter ID to search: ";
            cin >> id;
            inv.searchItem(id);
            break;
        case 4:
            inv.showAllItems();
            break;
        case 5:
            cout << "Exiting program...\n";
            break;
        default:
            cout << "Invalid choice. Try again.\n";
        }
    } while (choice != 5);

    return 0;
}
