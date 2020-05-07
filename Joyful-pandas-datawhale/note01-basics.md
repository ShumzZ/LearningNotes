- IO
 - read
   - csv
        `pd.read_csv('path_to_file.csv')`
   - txt
        `pd.read_table('path_to_file.txt')`
   - xls or xlsx (requires xlrd library)`
        `pd.read_excel('path_to_file.xslx')`
 - write
   - csv
        `pd.to_csv('path_to_file.csv')`
   - xls or xlsx (requires openyxl library)
        `pd.to_excel('path_to_file.xlsx', sheet_name='Sheet_1')`

- Basic Data structure
  - Series
    - create a series: values, index, name and dtype
        `s = pd.Series(np.random.rand(5), index=['a', 'b', 'c', 'd', 'e'], name='this is a series', dtype='float64')`
    - common attributes
        `s.values s.name s.index, s.dtype`
    - access element
        `s['b']`
    - common methods
        `s.mean(), s.mad()`
    - tons of attributes/ methods to explore:
        `dir(s)`
  - Dataframe
    - create a dataframe using dict
        `pd.DataFrame({'col1':list('abcde'),'col2':range(5,10),'col3':[1.3,2.5,3.6,4.6,5.8]},index=list('一二三四五'))`
    - take out a series from dataframe
        `df[col1]`
    - rename column or index
        `df.rename(index={'一':'one','二':'two'}, columns={'col1':'new_col1'})`
    - common attributes and methods
        `df.index df.columns df.values df.shape df.mean() sum/mean/median/mad/min/max/abs/std/var/quantile/cummax/cumsum/cumprod`
    - axes alignment, as [official doc](https://pandas.pydata.org/pandas-docs/stable/getting_started/dsintro.html?highlight=axis%20align#data-alignment-and-arithmetic) puts it: "data alignment is intrinsic. The link between labels and data will not be broken unless done so explicitly by you"
    - delete
        `df.drop(index='五', columns='new_col1') # inplace=False by default`
        `del df['new_col1'] # inplace by default`
        `df.pop('new_col1') # inplace`
    - add
        `df['new_col4'] = list('abc') # indexnot aligned`
        `df.assign(C=pd.Series(list('def'))) # index aligned, not inplace, return new df`
    - select columns by type
        `df.select_dtypes(include=['number'])`
    - series to Dataframe
        `s.to_frame()`

- Basic functions
 - head and tail
    `df.head(10) # first 10 rows, both df and series
    `df.tail(5) # last 5 rows, both df and series
 - unique and nunique
    `df['col1'].unique() # returns a ndarray with unique values for the series, INCLUDES NA values`
    `df['col2'].nunique() # returns the count of unique values, either an int (for series) or series (for df), EXCLUDES NA values`
 - count and value_counts
    `df['col2'].count() # returns a ndarray for series or series for df, the count of non-NA cells along a given axis`
    `df['col3'].value_counts() # return a series of counts for unique values`
 - info and describe
    `df.info() # much like pysparkdf.printSchema()`
    `df.describe() # can be used on numerical or non numerical columns`
 - idxmax and nlargest
    `df['Math'].idxmax() #  return the index of the first occurance of the maximum value over requested axis`
    skip NA by default skipna=False, otherwise return NA. If entire series is NA, return NA. Also note weirdly this won't work for strings (i.e. dtype=object), one of the [work arounds](https://stackoverflow.com/questions/49759346/pandas-serie-idxmax-fails-when-dtype-is-dtypeo) is `s.index[s.values.argmax()]` given s is a Series
    `df['Math'].nlargest(3)`
 - clip and replace
    `df['Math'].clip(33,80) # filter out rows with value lower than 33 and higher than 80`
1. clip defaults to trim along rows (axis=0)
2. if different lower/upper bounds are desired, pass in series
3. make sure index is aligned when pass in series
        `test = pd.DataFrame({'a':[3,-5,0,-9],'b':[8,3,-4,-6],'c':[0,8,3,-5]})`
        `s = pd.Series([-2,-1,5],index=['a','b','c'])`
        `test.clip(s,s+4,axis=1)`
 - replace:
   - return a serie:
        `df['Address'].replace(['street_1','street_2'], ['one','two'])`
   - or alter dataframe inplace:
        `df.replace({'Address':{'street_1':'one', 'street_2':'two'}})`
 - apply
   - For seires: apply a built-in or customized Python function or Numpy function to every value of the series; if a `collections.abc.Mapping` subclass is requried to pass in, use `Series.map()`
   - For dataframe: apply a function along an axis of the dataframe, i.e. `axis=0` will apply the func to each column, `axis=1` will apply the func to each row

- sorting
 - index sorting
    `df.set_index('Math').head(5)`
    `df.set_index('Math').sort_index(ascending=True).head(5)`

 - value sorting
    `df.sort_values(by='Class').head(5)`
    `df.sort_values(by=['Address', 'Height']).head(5)`
