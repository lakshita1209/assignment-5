#include <iostream>
#include <vector>
#include <string>

using namespace std;

struct Bus
{
    string number;
    string destination;
    string departureTime;
    int availableSeats;
};

struct Ticket
{
    string passengerName;
    string busNumber;
};

void viewBusTimings(const vector<Bus> &buses);
void buyTicket(vector<Bus> &buses, vector<Ticket> &tickets);

int main()
{
    vector<Bus> buses = {
        {"TN01A1234", "Chennai", "10:00 AM", 10},
        {"TN02B5678", "Coimbatore", "2:00 PM", 15},
        {"TN03C9101", "Madurai", "6:00 PM", 20}};
    vector<Ticket> tickets;
    int choice;

    while (true)
    {
        cout << "\nBus Ticket System\n";
        cout << "1. View Bus Timings\n";
        cout << "2. Buy Ticket\n";
        cout << "3. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice)
        {
        case 1:
            viewBusTimings(buses);
            break;
        case 2:
            buyTicket(buses, tickets);
            break;
        case 3:
            cout << "Exiting...\n";
            return 0;
        default:
            cout << "Invalid choice. Please try again.\n";
        }
    }

    return 0;
}

void viewBusTimings(const vector<Bus> &buses)
{
    cout << "\nBus Timings:\n";
    for (const auto &bus : buses)
    {
        cout << "Bus Number: " << bus.number << ", Destination: " << bus.destination
             << ", Departure Time: " << bus.departureTime << ", Available Seats: " << bus.availableSeats << endl;
    }
}

void buyTicket(vector<Bus> &buses, vector<Ticket> &tickets)
{
    string busNumber, passengerName;
    cout << "Enter bus number: ";
    cin >> busNumber;

    bool busFound = false;
    for (auto &bus : buses)
    {
        if (bus.number == busNumber)
        {
            if (bus.availableSeats > 0)
            {
                cout << "Enter passenger name: ";
                cin.ignore();
                getline(cin, passengerName);
                tickets.push_back({passengerName, busNumber});
                bus.availableSeats--;
                cout << "Ticket purchased successfully!\n";
            }
            else
            {
                cout << "Sorry, no available seats on this bus.\n";
            }
            busFound = true;
            break;
        }
    }

    if (!busFound)
    {
        cout << "Bus number not found.\n";
    }
}