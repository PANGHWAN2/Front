<template>
  <div>
    <h4>A05 ContactView</h4>
    <div >
        <table class="table">
            <tbody>
                <tr class="active">
                    <td>일련번호</td>
                    <td>{{person.no}}</td>
                </tr>
                <tr class="active">
                    <td>이름</td>
                    <td>{{person.name}}</td>
                </tr>
                <tr class="active">
                    <td>전화</td>
                    <td>{{person.tel}}</td>
                </tr>
                <tr class="active">
                    <td>주소</td>
                    <td>{{person.address}}</td>
                </tr>
            </tbody>
        </table>
    </div>
  </div>
</template>

<script>
import contactlist from './data/ContactList';

export default {
    data : function() {
        return {
            contacts : contactlist.contacts
        }
    },
    computed : {
        person() {
            const index = this.contacts.findIndex( item => item.no === Number(this.$route.params.id) );
            return this.contacts[index];
        }
    }
}
</script>
