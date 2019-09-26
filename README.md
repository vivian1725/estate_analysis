# 高雄市房價分析

* 使用公開資料查詢 https://plvr.land.moi.gov.tw 以年＋季 為查詢條件可下載zip檔
* 資料由101年開始到108年第二季
* 載回來後為CSV檔案

# 解壓縮到資料夾
* x_lvr_land_a：房屋買賣交易 / x_lvr_land_b：新成屋交易 / x_lvr_land_c：租房交易

```python
for d in dirs:
    print(d)
    df = pd.read_csv(os.path.join(d,estate_location), index_col=False)
    df['Q'] = d[-1]
    dfs.append(df.iloc[1:])
    
df = pd.concat(dfs, sort=True)
```
