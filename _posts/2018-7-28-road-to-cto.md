---
layout: post
title: "通往CTO之路"
author: "Zhangchunxin"
react: true
categories: work
tags: [工作,职业规划]
image: https://img.zhangchunxin.com/blog/2018-07-28-road-to-cto/00.jpg
---

最近在InfoQ的[《架构师》](http://www.infoq.com/cn/minibooks/architect-201807)上读了一篇文章，叫《你的能力模型决定了你的职位》，作者易观CTO 郭炜。

这篇文章使我的职业规划更加清晰明确。

没错，**我将来是要成为一名CTO的男人！**（*注意断句*）

在《你的能力模型决定了你的职位》文章中，作者提到了5个方面的能力模型：

 - **领导力** —— “成事”的能力
 - **文化构造能力** —— “影响意识”的能力
 - **人员管理能力** —— “人*100”的能力
 - **体系搭建能力** —— “建巢、管事”的能力
 - **技术实力** —— “技术肌肉”的实力

针对这5中能力，作者分别绘制了技术总监、技术VP、首席架构师和CTO的能力模型雷达图：

 - 技术总监
    <div id="tv-radar-chart" class="radar-chart"></div>
 - 技术VP
    <div id="vp-radar-chart" class="radar-chart"></div>
 - 首席架构师
    <div id="ca-radar-chart" class="radar-chart"></div>
 - CTO
    <div id="cto-radar-chart" class="radar-chart"></div>

回顾在华为近三年的工作，从管理岗转型为技术岗，虽然被任命为“架构师”，但我知道自己的能力离真正意义上的“架构师”仍有很大差距，这种差距让我有非常强烈的危机感，同时也很迷茫。

感谢郭炜的这篇文章和能力模型雷达图，让我清楚意识到能力差距和需要努力的方向。

---

以下是我针对CTO之路的一些思考、目标和计划。

1. **夯实技术基础能力，扩展视野**  
**目标**：作为CTO，技术不一定是公司最强的，但我还是要给自己定一个，打算**成为部门最强**。  
**计划**：  
  - 将工作中使用到的微服务技术栈夯实，补齐短板
  - 根据自己的兴趣爱好，扩展技术视野，学习研究热点技术
  
2. **加强团队技术氛围，锻炼体系搭建能力**  
在华为研发体系，一直是“流程”在约束团队能够高质量、高效的产出。但是，随着公司的流程减负、DevOps的推行，一夜之间每个人都开始反感流程。没了流程的约束，团队的产出效率高了，但是质量下降非常严重。  
**目标**：我现在对流程要求太过苛刻，造成团队氛围比较压抑，因此我打算**先成为团队成员喜欢的技术带头人**。
**计划**：  
 - 转变严苛的流程要求，以积极的态度影响团队成员的技术能力
 - 搭建一套强于流程的体系，让每个人能够感觉到自由，又能保证质量(需要进一步思考，有了想法会再写博客)  

3. **通过MBA学习，增强领导力、文化构建能力和人员管理能力**   
去年[机缘巧合被西交大MBA录取](#)，今年9月即将开学，我相信会有很多相关的知识等着我去学习和掌握，也会有很多活动等着我去实践和吸收，更会有很多人等着我去沟通和结交。  
**目标**：这个目标就是**好好学习，好好参与，好好做人**。

我对这条通往CTO之路充满了信心，我相信路的终点会有高山，也有彩虹。


<script type="text/babel">
const {Radar, RadarChart, PolarGrid, Tooltip,
         PolarAngleAxis, PolarRadiusAxis, ResponsiveContainer} = Recharts;

const data = [
    { subject: '领导力', tv: 4, vp: 6, ca: 4, cto: 9 },
    { subject: '文化构造能力', tv: 2, vp: 5, ca: 3, cto: 9 },
    { subject: '人员管理能力', tv: 7, vp: 8, ca: 6, cto: 9 },
    { subject: '体系搭建能力', tv: 3, vp: 9, ca: 7, cto: 8 },
    { subject: '技术实力', tv: 7, vp: 8, ca: 9, cto: 8 },
];

const TVRadarChart = React.createClass({
	render () {
  	return (
	<ResponsiveContainer width="100%" aspect={4.0/3.0}>
        <RadarChart data={data}>
          <PolarGrid />
          <PolarAngleAxis dataKey="subject" />
          <PolarRadiusAxis angle={90} domain={[0,10]} orientation="left" />
          <Tooltip />
          <Radar name="技术总监" dataKey="tv" stroke="#8884d8" fill="#8884d8" fillOpacity={0.6} />
        </RadarChart>
	</ResponsiveContainer>
    );
  }
})

const VPRadarChart = React.createClass({
	render () {
  	return (
	<ResponsiveContainer width="100%" aspect={4.0/3.0}>
        <RadarChart data={data}>
          <PolarGrid />
          <PolarAngleAxis dataKey="subject" />
          <PolarRadiusAxis angle={90} domain={[0,10]} orientation="left" />
          <Tooltip />
          <Radar name="技术VP" dataKey="vp" stroke="#8884d8" fill="#8884d8" fillOpacity={0.6} />
        </RadarChart>
	</ResponsiveContainer>
    );
  }
})

const CARadarChart = React.createClass({
	render () {
  	return (
	<ResponsiveContainer width="100%" aspect={4.0/3.0}>
        <RadarChart data={data}>
          <PolarGrid />
          <PolarAngleAxis dataKey="subject" />
          <PolarRadiusAxis angle={90} domain={[0,10]} orientation="left" />
          <Tooltip />
          <Radar name="首席架构师" dataKey="ca" stroke="#8884d8" fill="#8884d8" fillOpacity={0.6} />
        </RadarChart>
	</ResponsiveContainer>
    );
  }
})

const CTORadarChart = React.createClass({
	render () {
  	return (
	<ResponsiveContainer width="100%" aspect={4.0/3.0}>
        <RadarChart data={data}>
          <PolarGrid />
          <PolarAngleAxis dataKey="subject" />
          <PolarRadiusAxis angle={90} domain={[0,10]} orientation="left" />
          <Tooltip />
          <Radar name="CTO" dataKey="cto" stroke="#8884d8" fill="#8884d8" fillOpacity={0.6} />
        </RadarChart>
	</ResponsiveContainer>
    );
  }
})

ReactDOM.render(
  <TVRadarChart />,
  document.getElementById('tv-radar-chart')
);
ReactDOM.render(
  <VPRadarChart />,
  document.getElementById('vp-radar-chart')
);
ReactDOM.render(
  <CARadarChart />,
  document.getElementById('ca-radar-chart')
);
ReactDOM.render(
  <CTORadarChart />,
  document.getElementById('cto-radar-chart')
);
</script>
