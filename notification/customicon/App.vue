﻿<template>
    <div>
        <JqxNotification :theme="'material'" ref="myNotification"
                         :icon="{ width: 25, height: 25, url: 'https://www.jqwidgets.com/vue/images/smiley.png', padding: 5}"
                         :template="null"
                         :opacity="0.9"
                         :position="'top-left'"
                         :width="'auto'">
            <div>
                Thank you for your feedback!
            </div>
        </JqxNotification>
        <table style="margin-left: 15px; margin-top: 15px;">
            <tr>
                <td class="label">
                    Name:
                </td>
                <td>
                    <JqxInput :theme="'material'" ref="name" :width="150"></JqxInput>
                </td>
            </tr>
            <tr>
                <td class="label">
                    E-mail:
                </td>
                <td>
                    <JqxInput :theme="'material'" ref="email" :width="150"></JqxInput>
                </td>
            </tr>
            <tr>
                <td class="label" style="vertical-align: top;">
                    Comment:
                </td>
                <td>
                    <JqxTextArea :theme="'material'" ref="comment" :width="155" :height="150"></JqxTextArea>
                </td>
            </tr>
            <tr>
                <td colspan="2"></td>
            </tr>
            <tr>
                <td colspan="2" style="text-align: center;">
                    <JqxButton :theme="'material'" @click="click()">Submit comment</JqxButton>
                </td>
            </tr>
        </table>
    </div>
</template>
<script>
    import JqxNotification from "jqwidgets-scripts/jqwidgets-vue/vue_jqxnotification.vue";
    import JqxInput from "jqwidgets-scripts/jqwidgets-vue/vue_jqxinput.vue";
    import JqxTextArea from "jqwidgets-scripts/jqwidgets-vue/vue_jqxtextarea.vue";
    import JqxButton from "jqwidgets-scripts/jqwidgets-vue/vue_jqxbuttons.vue";

    export default {
        components: {
            JqxNotification,
            JqxInput,
            JqxTextArea,
            JqxButton
        },
        methods: {
            click: function () {
                this.$refs.name.val('');
                this.$refs.email.val('');
                this.$refs.comment.val('');
                this.$refs.myNotification.open();
            }
        }
    }
</script>

<style>
  
    .jqx-button {
        width: fit-content;
    }

    html, body {
        width: 100vw;
        height: 100vh;
        padding: 0;
        margin: 0;
    }

    .label {
        text-align: right;
    }
  
</style>
