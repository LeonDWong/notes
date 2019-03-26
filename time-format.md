date.toLocaleDateString("zh-cn", {  
    year: "numeric", month: "2-digit",  
    day: "2-digit", hour: "numeric", hour12:false, minute: "2-digit"  
}); // XXXX-XX-XX XX:XX like 2017/03/02 17:54

**BUT**, not compatible for IE lower than 11, Crap.
