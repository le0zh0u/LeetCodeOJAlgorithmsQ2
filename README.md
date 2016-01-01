# LeetCodeOJAlgorithmsQ2
LeetCodeOJ Algorithms Question2

Algorithms Querstion2:

You are given two linked lists representing two non-negative numbers. The digits fare stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

**Input:** (2 -> 4 -> 3) + (5 -> 6 -> 4)
**Output:** 7 -> 0 -> 8

thinking :

	not finished has error
	
code :
	
	/**
 	* Definition for singly-linked list.
 	* public class ListNode {
 	*     int val;
 	*     ListNode next;
 	*     ListNode(int x) { val = x; }
 	* }
 	*/
	public class Solution {
   	 public ListNode addTwoNumbers(ListNode l1, ListNode 	l2) {
        ListNode resultList = null;
        int temp = 0;
        while(l1!=null || l2!=null){
            int addResult = (l1!=null ? l1.val : 0) + (l2!=null ? l2.val : 0);
            int addResult2 = addResult % 10;
            if(resultList == null){
                	resultList = new ListNode(addResult2);
            	}else{
                	ListNode nextNode = new ListNode(temp == 1? addResult2+1 : addResult2);
                	resultList.next = nextNode;
                	resultList = nextNode;
            	}
            	if(l1!=null){
                	l1 = l1.next;
            	}
            	if(l2 != null){
                	l2 = l2.next;
            	}
            	if(addResult > 10){
                	temp = 1;
            	}else{
                	temp = 0;
            	}
        	}
        	if(temp == 1){
            	if(resultList == null){
                	resultList = new ListNode(1);
            	}else{
                	ListNode nextNode = new ListNode(1);
                	resultList.next = nextNode;
                	resultList = nextNode;
            	}
        	}
        
        	return resultList;
    	}
	}

