# SQL SERVER TEMP_DB PROPERTY
        DADOS DA TABELA TEMPORARIA

        SELECT 
             [column] = c.name, 
               [type] = t.name, c.max_length, c.precision, c.scale, c.is_nullable 
        FROM 
            tempdb.sys.columns AS c
        INNER JOIN tempdb.sys.types AS t ON c.system_type_id = t.system_type_id
            AND t.system_type_id = t.user_type_id
            WHERE [object_id] = OBJECT_ID(N'tempdb.dbo.#TESTE');
