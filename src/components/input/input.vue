<template>
    <div :class="wrapClasses">
        <input
            :class="classes"
            :type="type"
            :placeholder="placeholder"
            :name="name"
            v-model="value">
    </div>
</template>
<script>
    import { oneOf } from '../../utils/assist';

    const prefixCls = 'ivu-input';

    export default {
        props: {
            type: {
                type: String,
                default: 'text'
            },
            value: {
                type: [String, Number],
                default: '',
                twoWay: true
            },
            placeholder: String,
            name: String,
            size: {
                validator (value) {
                    return oneOf(value, ['small', 'large']);
                }
            }
        },
        data () {
            return {
            
            }        
        },
        computed: {
            wrapClasses () {

            },
            classes () {
                return [
                    `${prefixCls}`,
                    {
                        [`${prefixCls}-${this.size}`]: !!this.size
                    }
                ]
            }
        }
    }
</script>