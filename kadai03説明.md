# 手順
1. 図形を決める
2. 図形のパラメータを調べる
   - https://threejs.org/docs/#api/en/geometries/TorusGeometry 
3. 図形のパラメータをクラスとして書く
  ```js
var Torus = function (parameter) {
this.radius = parameter.radius; //半径
this.tube = parameter.tube; //チューブ半径
this.radialSegments = parameter.radialSegments; //トラスの頂点の数
this.tubularSegments = parameter.tubularSegments;//チューブの頂点の数
this.arc = parameter.arc;
this.x = parameter.x;           //x座標
this.y = parameter.y;           //y座標
this.z = parameter.z;           //z座標

//プロットデータ配列の初期化
data_x = [];
data_y = [];
data_z = [];

//プロットデータ配列に初期値を代入
data_x.push([0, this.x]);
data_y.push([0, this.y]);
data_z.push([0, this.z]);
};
  ```
4. パラメータに合わせてスライダーを配置する
  ```html
<tr>
    <td>radius</td>
    <td>
      <div id="slider_radius" class="slider"></div>
    </td>
    <td><input type="text" value="" id="input_radius" class="number"></td>
</tr>
  ```

5. パラメータごとにスライダーの設定を行う
6. 図形をgeometryとmeshで定義する
7. 図形を一度消し、スライダーのパラメータを適応した新しい図形を追加する（loop）