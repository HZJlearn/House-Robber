# House-Robber
假设你是一个专业的小偷，打算洗劫一条街所有的房子。每个房子里有不同价值的宝物，但是如果你选择偷窃连续的两栋房子，就会触发警报系统，编程求出你最多可以偷窃价值多少的宝物？

int houseRob(vector<int>& nums)
  {
       int n=nums.size();
       if(n==0)
          return 0;
       vector<int> memo(n,-1);
       for(i=n-2;i>=0;i--)
            for(j=i;j<n;j++)
                   memo[i]=max(memo[i],nums[j]+(j+2<n ? memo[j+2] : 0));
       return memo[0];
  
  }
