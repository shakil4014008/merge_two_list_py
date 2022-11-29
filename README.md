# merge_two_list_py

````py

def merge(s1, s2):
  r1, r2 = {}, {}
  
  for ch in s1: 
      r1[ch] = r1.get(ch, 0) + 1
  for ch in s2: 
      r2[ch] = r2.get(ch, 0) + 1

  p1, p2, res = 0, 0, []

  while p1 <len(s1) and p2 < len(s2):
      if r1[s1[p1]] < r2[s2[p2]]:
          res.append(s1[p1])
          p1 += 1
      elif r1[s1[p1]] > r2[s2[p2]]:
          res.append(s2[p2])
          p2 += 1
      else:
          if s1[p1] < s2[p2]:
              res.append(s1[p1])
              p1 += 1
          elif s1[p1] > s2[p2]:
              res.append(s2[p2])
              p2 += 1
  while p1 < len(s1):  # here while is needed to make sure, any remaining s1
      res.append(s2[p1])
      p1 += 1
  while p2 < len(s2): # here while is needed to make sure, any remaining s1
      res.append(s2[p2])
      p2 += 1
  return "".join(res)

s1 = "super"
s2 = "tower"
print(merge(s1, s2))
````
