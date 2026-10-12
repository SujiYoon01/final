header.forEach((h,idx)=>{ obj[h] = rows[r][idx]!==undefined ? rows[r][idx].trim() : ''; });
    if(NAME_DEPT_OVERRIDE[obj['이름']] && NAME_DEPT_OVERRIDE_FROM.includes(obj['부서명'])) obj['부서명'] = NAME_DEPT_OVERRIDE[obj['이름']];
