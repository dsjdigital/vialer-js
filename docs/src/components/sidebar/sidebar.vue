<component class="component-sidebar">
    <header class="header">
        <div class="header-logo">
            <router-link to="/">
                <img src="/img/logo-128.png"/>
            </router-link>
        </div>
        <div class="header-title">{{vendor.name}}</div>
        <div class="header-brand">Vialer-js {{version.current}}</div>
    </header>
    <nav class="navigation">
        <div class="navigation-header">User documentation</div>
        <router-link class="navigation-link" v-if="topic.name === 'introduction'" v-for="(topic, name) in topics.user" :to="{name: 'view_quickstart'}">
            {{topic.title}}
        </router-link>
        <router-link class="navigation-link" v-if="topic.name !== 'introduction'" :to="{name: 'view_user_topic', params: {topic_id: topic.name}}" v-for="(topic, name) in topics.user">
            {{topic.title}}
        </router-link>

        <div class="navigation-header">Developer documentation</div>
        <router-link class="navigation-link" :to="{name: 'view_developer_topic', params: {topic_id: topic.name}}" v-for="(topic, name) in topics.developer">
            {{topic.title}}
        </router-link>
    </nav>
</component>
