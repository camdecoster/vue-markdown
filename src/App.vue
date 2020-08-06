<template>
    <div id="app">
        <div class="container">
            <div class="row mt-4">
                <div class="col text-center">
                    <h1>
                        <b-badge class="text-align-center" variant="light">
                            Markdown Previewer
                        </b-badge>
                    </h1>
                </div>
            </div>
            <div class="row mt-4">
                <div class="col-md-6">
                    <div class="col text-center">
                        <h4>
                            <b-badge
                                class="text-align-center"
                                variant="secondary"
                            >
                                Markdown Input
                            </b-badge>
                        </h4>
                    </div>
                    <div class="mark-input" :style="inputStyle">
                        <textarea
                            class="input"
                            v-model="markdown"
                            style="padding: 10px"
                            :style="inputStyle"
                        >
                        </textarea>
                    </div>
                </div>

                <div class="col-md-6">
                    <div class="col text-center">
                        <h4>
                            <b-badge
                                class="text-align-center"
                                variant="secondary"
                            >
                                Preview
                            </b-badge>
                        </h4>
                    </div>
                    <div :style="outputStyle" v-html="compiledMarkdown"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
// Get the marked library for markdown conversion
import marked from "marked";

export default {
    name: "App",
    data() {
        return {
            inputStyle: {
                width: "400px",
                height: "50vh",
                marginLeft: "auto",
                marginRight: "auto",
            },
            outputStyle: {
                width: "400px",
                height: "50vh",
                backgroundColor: "#DCDCDC",
                marginLeft: "auto",
                marginRight: "auto",
                padding: "10px",
            },
            markdown: "# Hello World",
        };
    },
    computed: {
        // Compile the markdown text to HTML
        compiledMarkdown() {
            return marked(this.markdown);
        },
    },
};
</script>

<style></style>
