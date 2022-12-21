# bt_leetcode_b2
1.Maximum Number of Words Found in Sentences

    class Solution {
      int mostWordsFound(List<String> sentences) {
        int result = 0;
        for (int i = 0; i < sentences.length; i++)
        {
            if(sentences[i].split(" ").length >= result)
            {
                result = sentences[i].split(" ").length;
            }
        }
        return result;    
      }
    }

2.Sort the People

    class Solution {
      List<String> sortPeople(List<String> names, List<int> heights) {
        int s = 0;
        String str = "";
        for (int i = 0; i < heights.length - 1; i++)
        {
            for (int j = i + 1; j < heights.length; j++)
            {
                if (heights[i] < heights[j])
                {
                    //swap names
                    str = names[i];
                    names[i] = names[j];
                    names[j] = str;

                    //swap numbers
                    s = heights[i];
                    heights[i] = heights[j];
                    heights[j] = s;
                }
            }
        }
        return names;
      }
    }

3.Subtract the Product and Sum of Digits of an Integer

    class Solution {
        int subtractProductAndSum(int n) {
            int sum = 0, product = 1;
            while(n > 0) {
                sum += (n % 10);
                product *= (n % 10);
                n = n ~/ 10;
            }
            return (product - sum); 
        }
    }

4.Plus One

    class Solution {
      List<int> plusOne(List<int> digits) {
          for (var i = digits.length - 1; i >= 0; i--)
            {
                if (digits[i] != 9)
                {
                    digits[i]++;
                    return digits;
                }
                else
                    digits[i] = 0;
            }

            var res = digits.toList();
            res.insert(0, 1);
            return res;
      }
    }
