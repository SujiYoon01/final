header.forEach((h,idx)=>{ obj[h] = rows[r][idx]!==undefined ? rows[r][idx].trim() : ''; });
    if(obj['사번']) obj['사번'] = String(obj['사번']).replace(/\s+/g,'').replace(/\.0+$/,'').replace(/^0+/,'');
