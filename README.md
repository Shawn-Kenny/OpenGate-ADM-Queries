Select
MIS.APPL.database,
ADM.PAT.urn,
ADM.PAT.name,
ADM.PAT.acct.number
FROM MIS.APPL.main
JOIN ADM.PAT.room.bed.index ON MIS.APPL.main
JOIN ADM.PAT.main
WHERE MIS.APPL.database LIKE “ADM%”
AND { MIS.APPL.database=IF{O(#X),IF{O(%X),%.ADO.OPEN.DB(@MIS.APPL.database,”O(%X)”)}^ADO.ERR,
K(/[“ADO”].DB),M(#DB,/[“ADO”].DB),O(#X),ADO.ERR;MIS.APPL.database} }# OpenGate-ADM-Queries
A collection of ADM queries
