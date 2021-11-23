### TableComponent
```html
<TableList 
    :data="codegroupList"
    @row-click="onClickRow">
    <TableColumn label="CODEGROUPID"   prop="codeGroupId"/>
    <TableColumn label="CODEGROUPNAME" prop="codeGroupName"/>
    <TableColumn label="CREATED_DATE"  prop="timestamp"/>
    <TableColumn label="CODE USAGE"    prop="useYn"/>
    <template v-slot:header-append>
        <th scope="col"><a href="#none" @click="show = !show"><img src="/images/common/icon_link_btn_gray.png" alt="추가"></a></th>
    </template>
</TableList>
```
