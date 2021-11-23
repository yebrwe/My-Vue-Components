<script>
export default{
    props: {
        data: {
            type: Array,
            default: ()=> {
                return []
            }
        },
    },
    render() {
        const headers = this.$slots.default
            .filter(slot => slot.componentOptions)
            .map(({ componentOptions, data }) => {
                return {
                    ...componentOptions.propsData,
                    scopedSlots: data.scopedSlots && data.scopedSlots.default,
                }
            });
        return (
            <div class="table-box">
                <table class="table-box__type02">
                    <colgroup>
                        {
                            [
                                headers.map(header => <col width="*" key={header.key}/>),
                                this.$slots['header-append'] && <col width="3%"/>
                            ]
                        }
                    </colgroup>
                    <thead>
                        <tr>
                            {
                                [
                                    headers.map((header, index) =><th scope="col" width={header.width} key={index}>{header.label}</th>),
                                    this.$slots['header-append']
                                ]
                            }
                        </tr>
                    </thead>
                    <tbody>
                        {
                            this.data.length === 0 
                            ? <tr><td class="empty-data" colspan={headers.length + (this.$slots['header-append'] ? 1 : 0)}>No data available</td></tr>
                            : this.data.map(row => 
                                <tr 
                                    key={row._id}
                                    onClick={() => { this.$emit('row-click', row); }}>
                                        {
                                            headers.map((header, index) => {
                                                return header.scopedSlots 
                                                ? <td key={index}> { header.scopedSlots(row) } </td>
                                                : <td key={index}> { row[header.prop] }</td>
                                            })
                                        }
                                </tr>
                            )
                        }
                    </tbody>
                </table>
            </div>
        )
    },
}
</script>
