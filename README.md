# 24bda70111-cc-groupA-gagan-singh-exp2.3.2
# 24BDA70191-EXP-2.3.2-CC-GROUP-A
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
        // Step 1: Detect cycle using fast and slow pointers
        int slow = nums[0];
        int fast = nums[0];

        do {
            slow = nums[slow];
            fast = nums[nums[fast]];
        } while (slow != fast);

        // Step 2: Find the entrance to the cycle (the duplicate number)
        slow = nums[0];
        while (slow != fast) {
            slow = nums[slow];
            fast = nums[fast];
        }

        return slow;
    }
};
