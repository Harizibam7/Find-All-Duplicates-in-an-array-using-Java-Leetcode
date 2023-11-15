# Find-All-Duplicates-in-an-array-using-Java-Leetcode
    class Solution {
        public static void sort(int[] arr){
            int i =0;
            while(i < arr.length){
                int correct = arr[i]-1;
                if(arr[i]!=arr[correct]){
                    swap(arr, i , correct);
                }else{
                    i++;
                }
            }
        }
        public static void swap(int[] arr, int i , int correct){
            int temp;
            temp = arr[i];
            arr[i] = arr[correct];
            arr[correct] = temp;
        }
        public List<Integer> findDuplicates(int[] nums) {
            List<Integer> list = new ArrayList<>();
            Solution obj = new Solution();
            obj.sort(nums);
            for(int i =0; i<nums.length;i++){
                if(i+1 !=nums[i]){
                    list.add(nums[i]);
                }
            }
            return list;
        }
    
    }
