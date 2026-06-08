1.VALID ANAGRAM
class Solution {
public:
    bool isAnagram(string s, string t) {
        if(s.length() !=t.length()) return false;
        int arr[26]={0};
        for(int i=0;i<s.length();i++){
            arr[s[i]-'a']+=1;
            arr[t[i] - 'a']-=1;
        }
        for(int check : arr){
            if(check !=0) return false;
        }
        return true;
        
    }
};
2.FIRST UNIQUE CHARACTER IN A STRING:
class Solution {
public:
    int firstUniqChar(string s) {
        unordered_map<char, int>mp;

        for (auto a:s ) mp[a]++;
        for (int i=0; i < s.size();i++)if(mp[s[i]]==1)return i;
        return -1;
        
    }
};
3.RANSOM NOTE:
class Solution {
public:
    bool canConstruct(string ransomNote, string magazine) {
        
        unordered_map<char, int> count;

        for(char ch: magazine){
            count[ch] ++;
        }

        for(char ch: ransomNote){
            if(count[ch] == 0){
                return false;
            }
            count[ch]--;
        }
        return true;
    }
};
