<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">Add Resource</base-button>
    </base-card>
    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
</template>

<script>
import StoredResources from './StoredResources';
import AddResource from './AddResource';
export default {
    components:{
        StoredResources,
        AddResource,
    },
    data() {
        return{
            selectedTab: 'stored-resources',
            storedResources: [
                { 
                    id: 'official-guide', 
                    title:'Official Guide', 
                    description: 'The official Vue.js documentation.',
                    link: 'https://vuejs.org'
                },
                { 
                    id: 'google', 
                    title:'google', 
                    description: 'Learn to google...',
                    link: 'https://google.com'
                }
            ]
        };
    },
    computed:{
        storedResButtonMode() {
            return this.selectedTab === 'stored-resources' ? null : 'flat';
        },

        addResButtonMode() {
            return this.selectedTab === 'add-resource' ? null : 'flat';
        },
    },
    provide() {
        return {
            resources : this.storedResources,
            deleteResource : this.deleteResource
        };
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab; 
        },

        deleteResource (resId) {
            const resIndex = this.storedResources.findIndex(res => res.id === resId);
            this.storedResources.splice(resIndex, 1);
            console.log('test', resIndex);
            console.log('test2',  this.storedResources);
        }
    }
}
</script>
