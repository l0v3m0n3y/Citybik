# Citybik
api for citybik.es site for accessing CityBikes data including network information, station details, and field filtering.
# main
```cpp
#include "Citybik.h"
#include <iostream>

int main() {
   Citybik api;
    auto networks = api.networks_list().then([](json::value result) {
        std::cout << result<< std::endl;
    });
    networks.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```
