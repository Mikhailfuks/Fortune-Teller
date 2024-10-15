#include <iostream>
#include <string>
#include <vector>
#include <random>
#include <ctime>

using namespace std;

// Function to generate a random fortune
string generateFortune() {
    vector<string> fortunes = {
        "A new adventure is about to begin.",
        "You will find happiness in unexpected places.",
        "Your dreams are within reach, keep striving.",
        "Be cautious of those who seem too good to be true.",
        "A change is coming, embrace it with open arms.",
        "Success is on its way, be patient and persistent.",
        "Listen to your intuition, it will guide you.",
        "Love is in the air, be open to new connections.",
        "Your hard work will pay off in the end.",
        "Don't be afraid to take risks, they can lead to great rewards."
    };

    // Seed the random number generator
    random_device rd;
    mt19937 gen(rd());
    uniform_int_distribution<> distrib(0, fortunes.size() - 1);

    return fortunes[distrib(gen)];
}

int main() {
    cout << "Welcome to the Fortune Teller!" << endl;
    cout << "Ask your question and I will reveal your fortune..." << endl;

    string question;
    getline(cin, question);

    cout << "Your fortune is: " << generateFortune() << endl;

    return 0;
}

