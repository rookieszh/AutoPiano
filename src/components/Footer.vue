<style lang="less">
@import url('../assets/style/variable.less');
.component-page-footer { width: 100%; min-width: 1280px; height: 40px; line-height: 40px; background: rgba(255,255,255,.8); border-top: solid 1px #ccc; position: fixed; bottom: 0; text-align: center;
  .footer-ul { width: auto; height: 100%;
    .footer-item { display: inline; list-style: none; position: relative;
      a {
        &:hover { color: #fff; background: @c-blue; }
      }
      a.em { color: @c-red;
        &:hover { color: #fff; background: @c-red; }
      }
    }
  }
  .footer-ul.left-section { float: left; margin-left: 5%; }
  .footer-ul.right-section { float: right; margin-right: 5%; }

  .popup-container { width: 200px; height: 260px; position: absolute; top: -285px; left: 50%; transform: translateX(-50%); z-index: 200; background: rgba(255, 255, 255, 1); box-shadow: 1px 1px 10px 1px #ddd;
    &::after { content: ''; width: 20px; height: 20px; position: absolute;  left: 50%; bottom: -10px; transform: translateX(-50%) rotate(45deg); z-index: 150; background: rgba(255, 255, 255, 1); }
    .tab-wrap { width: 100%; height: 60px;
      .tab { width: 50%; height: 100%; float: left; cursor: pointer;
        &.active-tab { border-bottom: solid 5px @c-blue; }
        .icon { transform: scale(.5); transform-origin: 50% 0; margin-top: 14px; }
      }
    }
    .qrcode-wrap { width: 100%; padding: 12px 18px;
      .money { width: 100%; height: 14px; line-height: 14px; font-size: 14px; margin: 0; }
      .qrcode { width: 100%; }
    }
  }
}
</style>

<script>
export default {
  name: 'PageFooter',
  data() {
    return {
      supportShow: false,
      payType: 'WXPAY',
      aliPaySrc: require('../assets/images/aliqr.png'),
      wxPaySrc: require('../assets/images/wxqr.png')
    }
  },
  mounted() {},
  methods: {
    togglePayType (type) {
      this.payType = type
    },
    toggleSupportShow() {
      this.supportShow = !this.supportShow
    }
  }
}
</script>
