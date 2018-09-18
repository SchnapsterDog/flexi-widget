<template>
    <div class="flexi-widget">
        <div class="widget widget-stats"
             :class="dynamicColor">
            <div class="stats-content">
                <div class="flexi-widget-title">{{ header }}</div>
                <div class="flexi-widget-stats-number">{{ result }}</div>
                <div class="flexi-widget-stats-progress ">
                    <div class="flexi-progress-bar" style="width: 70.1%;"></div>
                </div>
                <div class="stats-desc">Better than last week {{ progressBar }} 70.1%</div>
            </div>
        </div>
    </div>
</template>
<script>
    /* Array
    * */
    let colorSelection = [
        {class: 'blue'}, {class: 'teal'}, {class: 'purple'}, {class: 'black'}
    ];

    /*  PROPS
        1. #color           @type String
        2. #header          @type String
        3. #result          @type Number
        4. #progressBar     @type Number
     */
    let props = {
        color: {
            type: String,
            default: 'blue',
            validator(color) {
                return ['blue', 'teal', 'purple', 'black'].indexOf(color) > -1;
            },
        },
        header: {
            type: String,
            default: 'Header',
        },
        result: {
            type: [String, Number],
            default: 2018
        },
        progressBar: {
            type: Number,
            default: 70.2
        }
    };


    export default {
        props,
        data() {
            return {
                colorSelection: colorSelection
            }
        },
        computed: {
            dynamicColor() {
                for (let i = 0; i < this.colorSelection.length; i++) {
                    if (this.color === this.colorSelection[i].class) {
                        return this.colorSelection[i].class;
                    }
                }
                return this.color.default;
            }
        }
    }
</script>
<style scoped>

    .flexi-widget {
        display: flex;
    }

    .widget {
        overflow: hidden;
        margin-bottom: 20px;
        background: #fff;
        color: inherit;
        padding: 0;
        border-radius: 0;
    }

    .widget.widget-stats {
        color: #fff;
        padding: 15px;
        border-radius: 3px;
    }

    .flexi-widget-title {
        color: #fff;
        color: rgba(255, 255, 255, .7);
    }

    .flexi-widget-stats-number {
        font-size: 24px;
        margin-bottom: 15px;
        font-weight: 600;
        letter-spacing: 1px;
    }

    .flexi-widget-stats-progress {
        background: rgba(0, 0, 0, .5);
        height: 2px;
        margin: 0 0 15px;
        border-radius: 3px;
    }

    .flexi-progress-bar {
        width: 70.1%;
        background: #fff;
        border-radius: 0 3px 3px 0;
    }

    .widget-stats .stats-desc {
        margin: -5px 0 -3px;
        font-weight: 300;
    }

    .teal {
        background: #34babb !important;
        background: -moz-linear-gradient(-45deg, rgba(52, 186, 187, 1) 0, rgba(0, 172, 172, 1) 100%) !important;
        background: -webkit-linear-gradient(-45deg, rgba(52, 186, 187, 1) 0, rgba(0, 172, 172, 1) 100%) !important;
        background: linear-gradient(135deg, rgba(52, 186, 187, 1) 0, rgba(0, 172, 172, 1) 100%) !important;
        filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#34babb', endColorstr='#00acac', GradientType=1) !important;
    }

    .blue {
        background: -moz-linear-gradient(-45deg, rgba(81, 136, 218, 1) 0, rgba(52, 135, 226, 1) 100%) !important;
        background: -webkit-linear-gradient(-45deg, rgba(81, 136, 218, 1) 0, rgba(52, 135, 226, 1) 100%) !important;
        background: linear-gradient(135deg, rgba(81, 136, 218, 1) 0, rgba(52, 135, 226, 1) 100%) !important;
        filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#5188da', endColorstr='#3487e2', GradientType=1) !important;
    }

    .purple {
        background: #8457f3 !important;
        background: -moz-linear-gradient(-45deg, rgba(132, 87, 243, 1) 0, rgba(114, 124, 182, 1) 100%) !important;
        background: -webkit-linear-gradient(-45deg, rgba(132, 87, 243, 1) 0, rgba(114, 124, 182, 1) 100%) !important;
        background: linear-gradient(135deg, rgba(132, 87, 243, 1) 0, rgba(114, 124, 182, 1) 100%) !important;
        filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#8457f3', endColorstr='#727cb6', GradientType=1) !important;
    }

    .black {
        background: #586169 !important;
        background: -moz-linear-gradient(-45deg, rgba(88, 97, 105, 1) 0, rgba(45, 53, 60, 1) 100%) !important;
        background: -webkit-linear-gradient(-45deg, rgba(88, 97, 105, 1) 0, rgba(45, 53, 60, 1) 100%) !important;
        background: linear-gradient(135deg, rgba(88, 97, 105, 1) 0, rgba(45, 53, 60, 1) 100%) !important;
        filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#586169', endColorstr='#2d353c', GradientType=1) !important;
    }
</style>
