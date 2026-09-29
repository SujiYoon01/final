// 기존
sel.innerHTML = '<option value="all">부서 전체</option>' + TEAM_LIST.map(t=>`<option value="${t}">${t}</option>`).join('');

// 변경
sel.innerHTML = (TEAM_LIST.length===1 ? '' : '<option value="all">부서 전체</option>') + TEAM_LIST.map(t=>`<option value="${t}">${t}</option>`).join('');
