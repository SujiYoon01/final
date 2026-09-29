  // 전월 데이터도 해당 부서만 남겨서 교체
  const markerPrev = 'const EMBEDDED_PREV_CSV = `';
  const startPrev = html.indexOf(markerPrev);
  if(startPrev!==-1){
    const prevTeamRows = PREV_RAW_ROWS.filter(r =>
      r['구분']!==EXCLUDE_WORKTYPE && !EXEC_RANKS.includes(r['직급']) &&
      !EXCLUDE_DEPT.includes(r['부서명']) && r['부서명']===team);
    let prevEsc = '';
    if(prevTeamRows.length){
      const pl = [header.join(',')];
      prevTeamRows.forEach(r=> pl.push(header.map(h=>escCell(r[h])).join(',')));
      prevEsc = ('\uFEFF'+pl.join('\r\n')).replace(/\\/g,'\\\\').replace(/`/g,'\\`').replace(/\$\{/g,'\\${');
    }
    const closePrev = html.indexOf('`;', startPrev+markerPrev.length);
    html = html.slice(0,startPrev) + markerPrev + prevEsc + html.slice(closePrev);
  }