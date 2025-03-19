```dataview
> > table WITHOUT ID file.link AS "三天内创建的笔记"
> > from ""
> > where date(today) - file.ctime <=dur(3 days)
> > sort file.ctime desc
> > limit 5
> > ```