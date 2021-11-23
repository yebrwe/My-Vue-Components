### Required
## Vue.js
## Nuxt.js
### Examples
```html
    <TemplatePageLayout title="Code Management">
        <div class="line-box">
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
        </div>
        <PopupCodegroupRegist :show.sync="show" @apply="getCodegroupList"/>
    </TemplatePageLayout>

    <TemplatePopupLayout
        title="Code Management Popup"
        :show="show"
        @apply="apply"
        @close="close"
    >
        <div class="line-box">
            <table class="form-table">
                <caption>기본정보에 관한 내용</caption>
                <colgroup>
                    <col width="*">
                </colgroup>
                <tbody>
                    <tr>
                        <td class="pad-lf-0">
                            <div class="form-wrap__item">
                                <div class="form-box">
                                    <input type="text" class="ipt-basic" placeholder="Code ID *" title="Code ID *" 
                                        v-model="code.codeId"
                                        ref="codeId"
                                        required/>
                                    <span class="underline-ani"></span>
                                </div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td class="pad-lf-0">
                            <div class="form-wrap__item">
                                <div class="form-box">
                                    <input type="text" class="ipt-basic" placeholder="Code Name *" title="Code Name *" 
                                        v-model="code.codeName"
                                        ref="codeName"
                                        required/>
                                    <span class="underline-ani"></span>
                                </div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td class="pad-lf-0">
                            <div class="form-wrap__item">
                                <div class="form-box">
                                    <input type="text" class="ipt-basic" placeholder="Code Desc *" title="Code Desc *" 
                                        v-model="code.codeDesc"
                                        ref="codeDesc"
                                        required/>
                                    <span class="underline-ani"></span>
                                </div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td class="pad-lf-0">
                            <div class="form-wrap__item">
                                <div class="form-box">
                                    <input type="number" class="ipt-basic" placeholder="Order *"  title="Order"
                                        v-model="code.order"
                                        ref="order"
                                        required/>
                                    <span class="underline-ani"></span>
                                </div>
                            </div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </TemplatePopupLayout>
```
