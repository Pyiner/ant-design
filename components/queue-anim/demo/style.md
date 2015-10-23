# style 自定义样式动画进出场

- order: 3

通过加上属性里的 `style` 来自定义 CSS 动画进出场。


---

````jsx
var QueueAnim = antd.QueueAnim;
var Button = antd.Button;
var Test = React.createClass({
  getInitialState() {
    return {
      show: true,
    }
  },
  onClick() {
    this.setState({
      show: !this.state.show,
    })
  },
  render() {
    return (
      <div>
        <div style={{marginBottom: 20}}>
          <Button type="primary" onClick={this.onClick}>切换</Button>
        </div>
        <QueueAnim className="demo-content" animConfig={[{opacity:[1, 0],translateY:[0, 50]},{opacity:[1, 0],translateY:[0, -50]}]}>
          {this.state.show ? [<div className="demo-kp" key='a'>
            <ul>
              <li></li>
              <li></li>
              <li></li>
            </ul>
          </div>,
            <div className="demo-listBox" key='b'>
              <div className="demo-list">
                <div className="title"></div>
                <ul>
                  <li></li>
                  <li></li>
                  <li></li>
                </ul>
              </div>
            </div>] : null}
        </QueueAnim>
      </div>
    )
  }
});

ReactDOM.render(<Test />
, document.getElementById('components-queue-anim-demo-style'));
````
gi
<style>
#components-queue-anim-demo-style {
  text-align: center;
  overflow: hidden;
  margin: 18px auto;
}
</style>