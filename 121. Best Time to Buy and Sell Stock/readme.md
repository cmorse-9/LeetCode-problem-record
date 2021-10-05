###121. Best Time to Buy and Sell Stock

Log:
Failed due to time complexity O(N^2/2)
In: C++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int profit = 0;
        for(int i = 0; i < prices.size(); i++){
            for(int j = i+1; j < prices.size(); j++){
                if((prices[j] - prices[i]) > profit){
                    profit = prices[j] - prices[i];
                }
            }
        }
        return profit;
    }
};


Dynamic Programming:
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int min = INT.MAX;
        int profit = 0;
        for(int i = 0; i < prices.size(); i++){
            for(int j = i+1; j < prices.size(); j++){
                if((prices[j] - prices[i]) > profit){
                    profit = prices[j] - prices[i];
                }
            }
        }
        return profit;
    }
};



