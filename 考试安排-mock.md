# 考试安排-mock

mock 路径: 考试报名 > 我的考试 > 考试安排查询

| 校区   | 考试校区 | 考试场次               | 课程编号  | 课程名称                      | 授课教师 | 考试时间               | 考场      |
|--------|--------|----------------------|-----------|-----------------------------|---------|----------------------|-----------|
| 主校区 | 主校区   | 管理学院1025          | 0700921   | 企业管理                    | 米振华   | 2024-10-25 12:30~14:10 | 1教D栋502 |
| 主校区 | 主校区   | 信息科学与工程学院1101 | 0300014   | 文献阅读与论文写作              | 谢雅     | 2024-11-01 12:30~14:10 | 1教D栋302 |
| 主校区 | 主校区   | 信息科学与工程学院1125 | L030750   | 人工智能                      | 何潇   | 2024-11-25 12:20~14:00 | 1教C栋506 |
| 主校区 | 主校区   | 信息科学与工程学院1129 | LS0303412 | 云计算与大数据B                | 肖鹏     | 2024-11-29 12:20~14:00 | 1教D栋503 |
| 主校区 | 主校区   | 信息科学与工程学院1203 | L030748   | 数字图像处理                  | 张鏖烽   | 2024-12-03 15:30~17:00 | 1教D栋502 |
| 主校区 | 主校区   | 信息科学与工程学院1218 | 0010001   | 大学生职业发展与就业指导（2）    | 陈致君   | 2024-12-18 14:00~16:00 | 1教D栋602 |
| 主校区 | 主校区   | 新工科·新文科建设1224  | 0000018   | 劳动理论                     | 谢雅   | 2024-12-24 10:50~12:30 | 1教D栋403 |
| 主校区 | 主校区   | 信息科学与工程学院0102 | 0300404   | 软件项目管理                  | 何潇   | 2025-01-02 16:10~18:10 | 1教D栋101 |
| 主校区 | 主校区   | 信息科学与工程学院0108 | 0300015   | 工程师职业道德与责任            | 郭鹏     | 2025-01-08 16:10~18:10 | 1教D栋403 |
| 主校区 | 主校区   | 信息科学与工程学院0113 | LS0303504 | 软件体系结构                  | 邬思奇   | 2025-01-13 08:30~10:30 | 1教D栋402 |


**快手那边**
| 校区   | 考试校区 | 考试场次               | 课程编号  | 课程名称                      | 授课教师 | 考试时间               | 考场      |
|--------|----------|------------------------|-----------|-------------------------------|----------|------------------------|-----------|
| 主校区 | 主校区   | 管理学院1025           | 0700921   | 企业管理                      | 米振华   | 2024-10-25 12:30~14:10 | 1教D栋502 |
| 主校区 | 主校区   | 信息科学与工程学院1031 | 0300014   | 文献阅读与论文写作            | 谢雅     | 2024-10-31 12:30~14:10 | 1教D栋302 |
| 主校区 | 主校区   | 信息科学与工程学院1031 | 0010001   | 大学生职业发展与就业指导（2） | 陈致君   | 2024-10-31 16:30~17:30 | 1教D栋401 |
| 主校区 | 主校区   | 信息科学与工程学院1108 | LS0303504 | 软件体系结构                  | 邬思奇   | 2024-11-08 14:30~16:10 | 1教C栋301 |
| 主校区 | 主校区   | 信息科学与工程学院1113 | 0300015   | 工程师职业道德与责任          | 郭鹏     | 2024-11-13 10:30~12:00 | 1教D栋502 |
| 主校区 | 主校区   | 信息科学与工程学院1121 | LS0303412 | 云计算与大数据B               | 肖鹏     | 2024-11-21 12:30~14:00 | 1教A栋401 |
| 主校区 | 主校区   | 信息科学与工程学院1203 | L030748   | 数字图像处理                  | 张鏖烽   | 2024-12-03 15:30~17:30 | 1教D栋401 |



```js
let mdText = `

`

const list = mdText.trim().split('\n').slice(2).map(line => line.trim().slice(1, -1).trim())
const data = list.map((e, idx) => {
	const [校区, 考试校区, 考试场次, 课程编号, 课程名称, 授课教师, 考试时间, 考场] = e.split('|').map(e => e.trim())
	return { 序号: idx + 1, 校区, 考试校区, 考试场次, 课程编号, 课程名称, 授课教师, 考试时间, 考场, 座位号: '', 准考证号: '', 备注: '' }
})
function buildTr(data) {
	const { 序号, 校区, 考试校区, 考试场次, 课程编号, 课程名称, 授课教师, 考试时间, 考场, 座位号, 准考证号, 备注 } = data
	return `<tr>
			<td>${序号}</td>
			<td align="left">${校区}</td>
			<td align="left">${考试校区}</td>
			<td align="left">${考试场次}</td>
			<td align="left">${课程编号}</td>
			<td align="left">${课程名称}</td>
			<td>${授课教师}</td>
			<td>${考试时间}</td>
			<td>${考场}</td>
			<td>${座位号}</td>
			<td>${准考证号}</td>
			<td>${备注}</td>
			<td><a href="javascript:0">备注</a></td>
		</tr>`
}

const header = `
<tr>
	<th class="Nsb_r_list_thb" style="width: 40px;">序号</th>
	<th class="Nsb_r_list_thb" style="width: 100px;">校区</th>
	<th class="Nsb_r_list_thb" style="width: 100px;">考试校区</th>
	<th class="Nsb_r_list_thb" style="width: 120px;">考试场次</th>
	<th class="Nsb_r_list_thb" style="width: 120px;">课程编号</th>
	<th class="Nsb_r_list_thb" style="width: 200px;">课程名称</th>
	<th class="Nsb_r_list_thb" style="width: 150px;">授课教师</th>
	<th class="Nsb_r_list_thb" style="width: 110px;">考试时间</th>
	<th class="Nsb_r_list_thb" style="width: 140px;">考场</th>
	<th class="Nsb_r_list_thb" style="width: 60px;">座位号</th>
	<th class="Nsb_r_list_thb" style="width: 120px;">准考证号</th>
	<th class="Nsb_r_list_thb" style="width: 120px;">备注</th>
	<th class="Nsb_r_list_thb" style="width: 50px;">操作</th>
</tr>
`
const dataEl = document.querySelector('#dataList tbody')
dataEl.innerHTML = header + data.map(buildTr).join('')
```
