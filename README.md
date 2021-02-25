原版地址: [UE4 Style Guide](https://github.com/Allar/ue4-style-guide#terms-cases)
------------------------
## Unreal Engine 4 Linter Plugin

[Unreal Engine 4 Linter Plugin](https://www.unrealengine.com/marketplace/linter-v2): 一个免费的自动检测代码风格的插件, 请使用市场版本UE。

## 0.原则：

这些原则参考自[idomatic.js style guide](https://github.com/rwaldron/idiomatic.js/)。

### 0.1: 遵循编码规范：

    如果你在一个项目上工作，或者与一个有预先存在的编码规范的团队一起工作， 现有的编码规范和本指南之间的任何不一致都应该服从现有的。

    编码规范应该是灵活的。 如果您认为更改对所有用法都有好处，您应该向现有的编码规范提出更改。

### 0.2: 统一：

    从一个项目转移到另一个项目不应该重新学习编码规范。 确定一种编码规范消除了不必要的麻烦。

    因为你不需要考虑规范，所以更有成效的创造和维护。 只需按照说明操作。 这个编码规范是用最好的实践编写的，这意味着通过遵循这个编码规范，您也将最小化难以跟踪的问题。

### 0.3：规范：

    如果你看到有人反对编码规范或没有编码规范，试着纠正它们。

    当在团队中工作或在诸如“虚幻者”这样的社区中讨论时，当人们保持一致时，帮助和寻求帮助要容易得多。 没有人喜欢帮助解开某人的意大利面条式的蓝图或处理资产的名字，他们无法理解。

    如果你正在帮助一个工作时不同但一致和理智的编码规范的人，你应该能够适应它。 如果它们不符合任何编码规范，请指出。

### 0.4：团队编码规范：

    当加入一个UE4团队时，你的第一个问题应该是“你有编码规范吗？“。 如果答案是否定的，你应该怀疑他们作为一个团队的工作能力。

### 0.5：不要违反规则：

Gamemakin LLC不是律师，但请不要给项目介绍非法动作和行为，包括但不限于：

    1. 不要分发你没有权利分发的内容；

    2. 不要侵犯他人的版权或商标材料；

    3. 不要窃取内容；

    4. 遵守对内容的许可限制。


## 1. 主要内容：

### 1.1：资产命名公约：

    命名公约应视为规则。 一个符合命名约定的项目能够轻松地管理、搜索、解析和维护其资产。

    大多数事物的前缀通常是资产类型的缩写，后面跟着下划线。

#### 1.1.1：基本资产名称：

    所有资产都应该有一个基本资产名称。 基本资产名称表示相关资产的逻辑分组。 任何属于这个逻辑组的资产都应该遵循 Prefix_BaseAssetName_Variant_Suffix

    对于资产的独特和特定的变量，Variant 要么是一个简短和易于识别的名称，它表示资产的逻辑分组，这些资产是资产基本名称的子集。 例如，如果Bob有多个皮肤，这些皮肤仍然应该使用Bob作为基本资产名称，但包括一个可识别的变体。 一个 Evil 皮肤将被称为 Bob_Evil 和 Retro 皮肤将被称为Bob_Retro。

    对于唯一的资产但通用的变量，Variant 是从01开始的两位数。 例如，如果你有一个环境艺术家产生不寻常的岩石，他们将被命名为 Rock_01，Rock_02，Rock_03 等。 除了罕见的例外，你不应该要求一个三位数的变体号码。 如果您有100多个资产，您应该考虑使用不同的基本名称或使用多个变体名称来组织它们。

    根据您的资产变量是如何制作的，您可以将变体名称链接在一起。 例如，如果您正在为Arch Viz项目创建地板资产，则应该使用带有链式变体的基本名称 Flooring，例如Flooring_Marble_01、Flooring_Maple_01、Flooring_Tile_Squares_01。

##### 1.1.1.1: 示例：

1.Bob:

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 180px 0 0 ">Asset Name</th>
    </tr>
    <tr>
        <td>Skeletal Mesh</td>
        <td>SK_Bob</td>
    </tr>
    <tr>
        <td>Material</td>
        <td>M_Bob</td>
    </tr>
    <tr>
        <td>Texture (Diffuse/Albedo)</td>
        <td>T_Bob_N</td>
    </tr>
    <tr>
        <td>Texture (Evil Diffuse)</td>
        <td>T_Bob_Evil_D</td>
    </tr>
</table>

2.Rocks:

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 180px 0 0 ">Asset Name</th>
    </tr>
    <tr>
        <td>Static Mesh (01)</td>
        <td>S_Rock_01</td>
    </tr>
    <tr>
        <td>Static Mesh (02)</td>
        <td>S_Rock_02</td>
    </tr>
    <tr>
        <td>Static Mesh (03)</td>
        <td>S_Rock_03</td>
    </tr>
    <tr>
        <td>Material</td>
        <td>M_Rock</td>
    </tr>
    <tr>
        <td>Material Instance (Snow)</td>
        <td>MI_Rock_Snow</td>
    </tr>
</table>

### 1.2：资产名称修饰符：

#### 1.2.1: Most Common：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Level / Map</td>
        <td></td>
        <td></td>
        <td>Should be in a folder called Maps</td>
    </tr>
    <tr>
        <td>Level (Persistent)</td>
        <td></td>
        <td>_P</td>
    </tr>
    <tr>
        <td>Level (Audio)</td>
        <td></td>
        <td>_Audio</td>
    </tr>
    <tr>
        <td>Level (Lighting)</td>
        <td></td>
        <td>_Lighting</td>
    </tr>
    <tr>
        <td>Level (Geometry)</td>
        <td></td>
        <td>_Geo</td>
    </tr>
    <tr>
        <td>Level (Gameplay)</td>
        <td></td>
        <td>_Gameplay</td>
    </tr>
    <tr>
        <td>Blueprint</td>
        <td>BP_</td>
    </tr>
    <tr>
        <td>Material</td>
        <td>M_</td>
    </tr>
    <tr>
        <td>Texture</td>
        <td>T_</td>
        <td>_?</td>
        <td>See 'Textures'</td>
    </tr>
    <tr>
        <td>Particle System</td>
        <td>PS_</td>
    </tr>
    <tr>
        <td>Widget Blueprint</td>
        <td>WBP_</td>
    </tr>
</table>

### 1.2.2: Animations：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Aim Offset</td>
        <td>AO_</td>
    </tr>
    <tr>
        <td>Aim Offset 1D</td>
        <td>AO_</td>
    </tr>
    <tr>
        <td>Animation Blueprint</td>
        <td>ABP_</td>
    </tr>
    <tr>
        <td>Animation Composite</td>
        <td></td>
        <td>AC_</td>
    </tr>
    <tr>
        <td>Animation Montage</td>
        <td>AM_</td>
    </tr>
    <tr>
        <td>Animation Sequence</td>
        <td>BS_</td>
    </tr>
    <tr>
        <td>Blend Space 1D</td>
        <td>BS_</td>
    </tr>
    <tr>
        <td>Level Sequence</td>
        <td>LS_</td>
    </tr>
    <tr>
        <td>Morph Target</td>
        <td>MT_</td>
    </tr>
    <tr>
        <td>Paper Flipbook</td>
        <td>PFB_</td>
    </tr>
    <tr>
        <td>Rig</td>
        <td>Rig_</td>
    </tr>
    <tr>
        <td>Skeletal Mesh</td>
        <td>SK_</td>
    </tr>
    <tr>
        <td>Skeleton</td>
        <td>SKEL_</td>
    </tr>
</table>

### 1.2.3 Artificial Intelligence：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>AI Controller</td>
        <td>AIC_</td>
    </tr>
    <tr>
        <td>Behavior Tree</td>
        <td>BT_</td>
    </tr>
    <tr>
        <td>Blackboard</td>
        <td>BB_</td>
    </tr>
    <tr>
        <td>Decorator</td>
        <td>BTDecorator_</td>
    </tr>
    <tr>
        <td>Service</td>
        <td>BTService_</td>
    </tr>
    <tr>
        <td>Task</td>
        <td>BTTask_</td>
    </tr>
    <tr>
        <td>Environment Query</td>
        <td>EQS_</td>
    </tr>
    <tr>
        <td>EnvQueryContext</td>
        <td>EQS_</td>
        <td>Context</td>
    </tr>
    <tr>
        <td>Texture</td>
        <td>T_</td>
        <td>_?</td>
        <td>See 'Textures'</td>
    </tr>
    <tr>
        <td>Particle System</td>
        <td>PS_</td>
    </tr>
    <tr>
        <td>Widget Blueprint</td>
        <td>WBP_</td>
    </tr>
</table>

#### 1.2.4 Blueprints：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Blueprint</td>
        <td>BP_</td>
    </tr>
    <tr>
        <td>Blueprint Component</td>
        <td>BP_</td>
        <td>Component</td>
        <td>I.e. BP_InventoryComponent</td>
    </tr>
    <tr>
        <td>Blueprint Function Library</td>
        <td>BPFL_</td>
    </tr>
    <tr>
        <td>Blueprint Interface</td>
        <td>BPI_</td>
    </tr>
    <tr>
        <td>Blueprint Macro Library</td>
        <td>BPML_</td>
        <td></td>
        <td>Do not use macro libraries if possible</td>
    </tr>
    <tr>
        <td>Enumeration</td>
        <td>E</td>
        <td></td>
        <td>No underscore</td>
    </tr>
    <tr>
        <td>Environment Query</td>
        <td>EQS_</td>
    </tr>
    <tr>
        <td>Structure</td>
        <td>F or S</td>
        <td></td>
        <td>No underscore</td>
    </tr>
    <tr>
        <td>Texture</td>
        <td>T_</td>
        <td>_?</td>
        <td>See 'Textures'</td>
    </tr>
    <tr>
        <td>Tutorial Blueprint</td>
        <td>TBP_</td>
    </tr>
    <tr>
        <td>Widget Blueprint</td>
        <td>WBP_</td>
    </tr>
    <tr>
        <td>Widget Blueprint</td>
        <td>WBP_</td>
    </tr>
</table>

### 1.2.5 Materials：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Material</td>
        <td>M_</td>
    </tr>
    <tr>
        <td>Material (Post Process)</td>
        <td>PP_</td>
    </tr>
    <tr>
        <td>Material Function</td>
        <td>MF_</td>
    </tr>
    <tr>
        <td>Material Instance</td>
        <td>MI_</td>
    </tr>
    <tr>
        <td>Material Parameter Collection</td>
        <td>MPC_</td>
    </tr>
    <tr>
        <td>Subsurface Profile</td>
        <td>SP_</td>
    </tr>
    <tr>
        <td>Physical Materials</td>
        <td>PM_</td>
    </tr>
    <tr>
        <td>Decal</td>
        <td>M_, MI_</td>
        <td>_Decal</td>
    </tr>
</table>

### 1.2.6 Textures：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Texture</td>
        <td>T_</td>
    </tr>
    <tr>
        <td>Texture (Diffuse/Albedo/Base Color)</td>
        <td>T_</td>
        <td>_D</td>
    </tr>
    <tr>
        <td>Texture (Normal)</td>
        <td>T_</td>
        <td>_N</td>
    </tr>
    <tr>
        <td>Texture (Roughness)</td>
        <td>T_</td>
        <td>_R</td>
    </tr>
    <tr>
        <td>Texture (Alpha/Opacity)</td>
        <td>T_</td>
        <td>_A</td>
    </tr>
    <tr>
        <td>Texture (Ambient Occlusion)</td>
        <td>T_</td>
        <td>_O</td>
    </tr>
    <tr>
        <td>Texture (Bump)</td>
        <td>T_</td>
        <td>_B</td>
    </tr>
    <tr>
        <td>Texture (Emissive)</td>
        <td>T_</td>
        <td>_E</td>
    </tr>
    <tr>
        <td>Texture (Mask)</td>
        <td>T_</td>
        <td>_M</td>
    </tr>
    <tr>
        <td>Texture (Specular)</td>
        <td>T_</td>
        <td>_S</td>
    </tr>
    <tr>
        <td>Texture (Metallic)</td>
        <td>T_</td>
        <td>_M</td>
    </tr>
    <tr>
        <td>Texture (Packed)</td>
        <td>T_</td>
        <td>_*</td>
        <td>See notes below about packing</td>
    </tr>
    <tr>
        <td>Texture Cube</td>
        <td>TC_</td>
    </tr>
    <tr>
        <td>Media Texture</td>
        <td>MT_</td>
    </tr>
    <tr>
        <td>Render Target</td>
        <td>RT_</td>
    </tr>
    <tr>
        <td>Cube Render Target</td>
        <td>RTC_</td>
    </tr>
    <tr>
        <td>Texture Light Profile</td>
        <td>TLP_</td>
    </tr>
</table>

#### 1.2.6.1 Texture Packing：

    将多层纹理数据打包成一个纹理是常见的做法。 这方面的一个例子是将表情、粗糙度、环境遮挡分别打包为纹理的红色、绿色和蓝色通道。 要确定后缀，只需将上面给定的后缀字母叠加在一起。

    在 Alpha / Albedo 的 alpha 通道中包含 Alpha / Opacity 层通常是可以接受的，由于这是常见的做法，在 _D 后缀中添加 A 是可选的。

### 1.2.7 Miscellaneous：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Animated Vector Field</td>
        <td>VFA_</td>
    </tr>
    <tr>
        <td>Camera Anim</td>
        <td>CA_</td>
    </tr>
    <tr>
        <td>Color Curve</td>
        <td>Curve_</td>
        <td>_Color</td>
    </tr>
    <tr>
        <td>Curve Table</td>
        <td>Curve_</td>
        <td>_Table</td>
    </tr>
    <tr>
        <td>Texture (Alpha/Opacity)</td>
        <td>T_</td>
        <td>_A</td>
    </tr>
    <tr>
        <td>Data Asset</td>
        <td>*_</td>
        <td></td>
        <td>Prefix should be based on class</td>
    </tr>
    <tr>
        <td>Data Table</td>
        <td>DT_</td>
    </tr>
    <tr>
        <td>Float Curve</td>
        <td>Curve_</td>
        <td>_Float</td>
    </tr>
    <tr>
        <td>Force Feedback Effect</td>
        <td>FFE_</td>
    </tr>
    <tr>
        <td>Landscape Grass Type</td>
        <td>LG_</td>
    </tr>
    <tr>
        <td>Landscape Layer</td>
        <td>LL_</td>
    </tr>
    <tr>
        <td>Matinee Data</td>
        <td>Matinee_</td>
    </tr>
    <tr>
        <td>Media Player</td>
        <td>MP_</td>
    </tr>
    <tr>
        <td>Object Library</td>
        <td>OL_</td>
    </tr>
    <tr>
        <td>Redirector	</td>
        <td></td>
        <td></td>
        <td>These should be fixed up ASAP</td>
    </tr>
    <tr>
        <td>Sprite Sheet</td>
        <td>SS_</td>
    </tr>
    <tr>
        <td>Static Vector Field</td>
        <td>VF_</td>
    </tr>
    <tr>
        <td>Substance Graph Instance</td>
        <td>SGI_</td>
    </tr>
    <tr>
        <td>Substance Instance Factory</td>
        <td>SIF_</td>
    </tr>
    <tr>
        <td>Touch Interface Setup</td>
        <td>TI_</td>
    </tr>
    <tr>
        <td>Vector Curve</td>
        <td>Curve_</td>
        <td>_Vector</td>
    </tr>
</table>

### 1.2.8 Paper 2D：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Paper Flipbook</td>
        <td>PFB_</td>
    </tr>
    <tr>
        <td>Sprite</td>
        <td>SPR_</td>
    </tr>
    <tr>
        <td>Sprite Atlas Group</td>
        <td>SPRG_</td>
    </tr>
    <tr>
        <td>Tile Map</td>
        <td>TM_</td>
    </tr>
    <tr>
        <td>Tile Set</td>
        <td>MPC_</td>
    </tr>
    <tr>
        <td>Subsurface Profile</td>
        <td>TS_</td>
    </tr>
    <tr>
        <td>Physical Materials</td>
        <td>PM_</td>
    </tr>
    <tr>
        <td>Decal</td>
        <td>M_, MI_</td>
        <td>_Decal</td>
    </tr>
</table>

### 1.2.9 Physics：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Physical Material</td>
        <td>PM_</td>
    </tr>
    <tr>
        <td>Physics Asset</td>
        <td>PHYS_</td>
    </tr>
    <tr>
        <td>Destructible Mesh</td>
        <td>DM_</td>
    </tr>
</table>

### 1.2.10 Sounds：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Dialogue Voice</td>
        <td>DV_</td>
    </tr>
    <tr>
        <td>Dialogue Wave</td>
        <td>DW_</td>
    </tr>
    <tr>
        <td>Media Sound Wave</td>
        <td>MSW_</td>
    </tr>
    <tr>
        <td>Reverb Effect</td>
        <td>Reverb_</td>
    </tr>
    <tr>
        <td>Sound Attenuation</td>
        <td>ATT_</td>
    </tr>
    <tr>
        <td>Sound Class</td>
        <td></td>
        <td></td>
        <td>No prefix/suffix. Should be put in a folder called SoundClasses</td>
    </tr>
    <tr>
        <td>Sound Concurrency</td>
        <td></td>
        <td>_SC</td>
        <td>Should be named after a SoundClass</td>
    </tr>
    <tr>
        <td>Sound Cue</td>
        <td>A_</td>
        <td>_Cue</td>
    </tr>
    <tr>
        <td>Sound Mix</td>
        <td>Mix_</td>
    </tr>
    <tr>
        <td>Sound Wave</td>
        <td>A_</td>
    </tr>
</table>

### 1.2.11 User Interface：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Font</td>
        <td>Font_</td>
    </tr>
    <tr>
        <td>Slate Brush</td>
        <td>Brush_</td>
    </tr>
    <tr>
        <td>Slate Widget Style</td>
        <td>Style_</td>
    </tr>
    <tr>
        <td>Widget Blueprint</td>
        <td>WBP_</td>
    </tr>
</table>

### 1.2.12 Effects：

<table style="margin-bottom: 10px">
    <tr>
        <th style="padding: 0 180px 0 0">Asset Type</th>
        <th style="padding: 0 50px 0 0 ">Prefix</th>
        <th style="padding: 0 50px 0 0 ">Suffix</th>
        <th style="padding: 0 50px 0 0 ">Notes</th>
    </tr>
    <tr>
        <td>Particle System</td>
        <td>PS_</td>
    </tr>
    <tr>
        <td>Material (Post Process)</td>
        <td>PP_</td>
    </tr>
</table>

## 2. 内容目录结构：

### 2e1 Example Project Content Structure：

    与资产名称同样重要的是，项目的目录结构样式应该被视为规则。 资产命名约定和内容目录结构是并行不悖的，两者的违反都会造成不必要的混乱。

    有多种方法来布局UE4项目的内容。 在这种风格中，我们将使用一个结构，它更多地依赖于 ContentBrowser 的过滤和搜索能力来帮助那些使用资产的人找到特定类型的资产，而不是另一个将资产类型与文件夹分组的通用结构。

```
|-- Content
    |-- GenericShooter
        |-- Art
        |   |-- Industrial
        |   |   |-- Ambient
        |   |   |-- Machinery
        |   |   |-- Pipes
        |   |-- Nature
        |   |   |-- Ambient
        |   |   |-- Foliage
        |   |   |-- Rocks
        |   |   |-- Trees
        |   |-- Office
        |-- Characters
        |   |-- Bob
        |   |-- Common
        |   |   |-- Animations
        |   |   |-- Audio
        |   |-- Jack
        |   |-- Steve
        |   |-- Zoe
        |-- Core
        |   |-- Characters
        |   |-- Engine
        |   |-- GameModes
        |   |-- Interactables
        |   |-- Pickups
        |   |-- Weapons
        |-- Effects
        |   |-- Electrical
        |   |-- Fire
        |   |-- Weather
        |-- Maps
        |   |-- Campaign1
        |   |-- Campaign2
        |-- MaterialLibrary
        |   |-- Debug
        |   |-- Metal
        |   |-- Paint
        |   |-- Utility
        |   |-- Weathering
        |-- Placeables
        |   |-- Pickups
        |-- Weapons
            |-- Common
            |-- Pistols
            |   |-- DesertEagle
            |   |-- RocketPistol
            |-- Rifles
```
这种结构的原因列于以下各小节。

### 2.1 文件夹名称：

这些是命名内容结构中任何文件夹的常用规则：

#### 2.1.1 总是使用Pascal Case：

    Pascal Case 是指用大写字母开始一个名字，然后不使用空格，下面的每个单词也以大写字母开始。 例如，DesertEagle，RocketPistol 和 ASeriesOfWords。

#### 2.1.2 不使用空格：

    强化2.1.1，绝不使用空格。 空间会导致各种工程工具和批处理过程失败。 理想情况下，项目的根也不包含空格，并且位于这样的位置 D:\Project 代替 C:\Users\My Name\My Documents\Unreal Projects。

#### 2.1.3 永远不要使用单极字符和其他符号：

    如果您的游戏角色之一名为“Zoe”，其文件夹名称应该是 Zoe。 对于工程工具，Unicode字符可能比Spaces更糟糕，UE4的某些部分也不支持路径中的Unicode字符。

    与此相关，如果您的项目有无法解释的问题，并且您的计算机的用户名具有 Unicode 字符(即。 您的名字是 Zoe )，位于您的“My Documents”文件夹中的任何项目都将受到此问题的影响。 通常简单地将您的项目移动到 D:\Project 将解决这些问题。

    使用 a-z 、 A-Z 和 0-9 以外的其他字符，如@、-、、*和#，也会导致意外和难以跟踪其他平台、源控制和较弱的工程工具上的问题。

#### 2.2 项目特定资产使用顶层文件夹：

    项目的所有资产都应该存在于以项目命名的文件夹中。 例如，如果您的项目名为“GenericShooter”，那么它的所有内容都应该存在于 Content/GenericShooter 中。

    Developers 不是用于项目依赖的资产，因此不是特定于项目的。 有关这方面的详细信息，请参阅开发人员文件夹。

这种做法有多种原因：

#### 2.2.1 没有全局资产：

    通常，在编码规范指南中，您不应该污染全局命名空间并需要遵循相同的原则。 当资产被允许存在于项目文件夹之外时，执行严格的结构布局往往变得更加困难，因为不在文件夹中的资产会鼓励不必组织资产的不良行为。

    每项资产都要有目的，否则不属于项目。 如果一个资产是一个实验测试，不应该被项目使用，它应该放在一个 Developer 文件夹中。

#### 2.2.2 减少迁移冲突：

    当处理多个项目时，团队通常会将资产从一个项目复制到另一个项目，如果它们对两者都有用的话。 当发生这种情况时，执行副本的最简单方法是使用Content Browser的迁移功能，因为它不仅会复制选定的资产，而且会复制所有依赖项。

    这些依赖关系很容易让你陷入麻烦。 如果两个项目的资产没有顶级文件夹，并且它们碰巧具有类似的命名或先前已迁移的资产，则新迁移可能会意外地擦除对现有资产的任何更改。

    这也是Epic的市场工作人员对提交的资产执行相同政策的主要原因。

    在迁移之后，可以使用内容浏览器中的“替换引用”工具进行资产的安全合并，因为不属于项目顶层文件夹的资产显然正在等待合并。 一旦资产被合并并完全迁移，就不应该在 Content 树中有另一个顶级文件夹。 该方法100%保证使任何发生的迁移完全安全。

##### 2.2.2e1 Master Material Example：

    例如，假设您在一个项目中创建了一个主材料，您希望在另一个项目中使用，以便将该资产迁移过来。 如果此资产不在顶级文件夹中，则可能有一个名称，如 Content/MaterialLibrary/M_Master 。 如果目标项目已经没有主材料，这应该是没有问题的。

    随着一个或两个项目的工作进展，由于正常的发展过程，它们各自的主要材料可能会改变，以适应它们的具体项目。

    例如，当一个项目的艺术家创建了一个很好的静态网格的通用模块化集合，并且有人希望在第二个项目中包含这组静态网格时，问题就出现了。 如果创建这些资产的艺术家按照指示使用基于 Content/Material Library/M_Master 的材料实例，那么在执行迁移时，以前迁移的 Content/Material Library/M Master 资产很有可能发生冲突。

    在这一点上，如果两个项目的主材料以任何方式不兼容，您可能会破坏项目的整个材料库以及可能已经迁移的任何其他依赖项，这仅仅是因为资产没有存储在顶级文件夹中。 静态网格的简单迁移现在成为一个非常丑陋的任务。

#### 2.2.3 样品、模板和市场内容是无风险的：

    扩展到2.2.2，如果团队成员决定添加示例内容、模板文件或示例内容、模板文件或资产，则可以保证，只要项目的顶级文件夹是唯一命名的，这些新资产就不会干扰您的项目。

    您不能信任市场内容完全符合顶级文件夹规则。 存在许多资产，它们的大部分内容在顶级文件夹中，但也可能修改Epic示例内容以及污染全局 Content 文件夹的级别文件。

    当坚持2.2，最糟糕的市场冲突，你可以有如果两个市场资产都有相同的史诗样本内容。 如果您的所有资产都在特定于项目的文件夹中，包括您可能已移动到文件夹中的示例内容，则项目将永远不会中断。

#### 2.2.4 DLC、子项目和补丁易于维护：

    如果您的项目计划发布DLC，或者有多个与它相关的子项目，这些子项目可能被迁移出去，或者根本不在构建中煮熟，那么与这些项目相关的资产应该有自己单独的顶层内容文件夹。 这使得烹饪DLC与主要项目内容分离得更容易。 子项目也可以在最少的努力下进行进出迁移。 如果您需要更改资产的材料或在补丁中添加一些非常特定的资产覆盖行为，您可以很容易地将这些更改放在补丁文件夹中，并安全地工作，而不会破坏核心项目。

### 2.3 使用开发人员文件夹进行本地测试：

    在项目开发过程中，团队成员有一种“sandbox”是非常常见的，他们可以在不冒核心项目风险的情况下自由地进行实验。 由于这项工作可能正在进行中，这些团队成员可能希望将他们的资产放在项目的源代码管理服务器上。 并不是所有的团队都需要使用 Developer 文件夹，但是使用它们的团队经常会遇到提交给源代码管理的资产的常见问题。

    团队成员很容易意外地使用尚未准备使用的资产，一旦这些资产被移除，这将导致问题。 例如，艺术家可能正在迭代一组模块化的静态网格，并仍在努力使其大小和网格抓取正确。 如果一个世界建设者在主项目文件夹中看到这些资产，他们可能会在一个层次上使用它们，而不知道它们可能会受到难以置信的更改和/或删除。 这导致团队中的每个人都需要解决大量的重新工作。

    如果这些模块化资产被放置在Developer文件夹中，世界建设者就不应该有理由使用它们，整个问题就永远不会发生。 Content Browser 有特定的 View Options ，它将隐藏 Developer 文件夹（默认情况下隐藏它们），不可能在正常使用下意外使用 Developer 资产。

    一旦资产准备好使用，艺术家只需将资产移动到项目特定文件夹并修复重定向器。 这基本上是“促进”资产从实验到生产。

###  2.4 所有的 Map* 文件属于一个名为Maps的文件夹：

    地图文件非常特殊，每个项目都有自己的地图命名系统是很常见的，特别是当它们与子级或流级一起工作时。 无论为特定项目建立了什么地图组织系统，所有级别都应该属于 /Content/Project/Maps。

    能够告诉某人打开一个特定的地图，而不必解释它在哪里是一个伟大的节省时间和一般的“生活质量”的改进。 层次通常位于地图的子文件夹中，例如 Maps/Campaign1/ 或 Maps/Arenas ，但这里最重要的是它们都存在于 /Content/Project/Maps 中。

    这也简化了工程师的工作。 如果必须为构建过程挖掘任意的文件夹，那么构建过程的摇摆级别可能非常令人沮丧。 如果一个团队的地图都在一个地方，那么不在构建中意外地绘制地图就会困难得多。 它还简化了照明构建脚本以及QA过程。

### 2.5 使用一个名叫 Core 的文件夹存放关键 Blueprints 和其他资产：

    使用/Content/Project/Core文件夹处理对项目工作绝对重要的资产。 例如，基本GameMode、Character、PlayerController、GameState、PlayerState 和相关的蓝图应该住在这里。

    这为其他团队成员创建了一个非常清晰的“不要触摸这些”信息。 非工程师应该没有什么理由进入 Core 文件夹。 遵循良好的代码结构风格，设计师应该在公开功能的子类中进行游戏调整。 世界建筑商应该在指定的文件夹中使用预制版蓝图，而不是潜在地滥用基类。

    例如，如果您的项目需要可以放置在一个级别中的 pickups ，那么在 Core/Pickups 中应该存在一个 base pickups 类，它定义了 pickups 的基本行为。特定的 pickups ，如健康或弹药，应该存在于一个文件夹中，如 /Content/Project/Placeables/Pickups/ 。游戏设计师可以定义和调整皮卡在这个文件夹，但他们不应该触摸 Core/Pickups，因为他们可能无意中打破 pickups 在整个项目

### 2.6 不要创建称为资产或资产类型的文件夹：

### 2.6.1 创建一个名为资产的文件夹是多余的：

所有资产都是资产。

#### 2.6.2 创建一个名为 Mesh 、Texure 或 Materials 的文件夹是多余的：

    所有资产名称都是以其资产类型命名的。 这些文件夹只提供冗余信息，这些文件夹的使用可以很容易地替换为内容浏览器提供的健壮和易于使用的过滤系统。

    只想查看环境/岩石中的静态网格/？ 只需打开静态网格过滤器。 如果所有资产都正确命名，它们也将按字母顺序排序，而不管前缀如何。 想查看静态网格和骨骼网格吗？ 只需打开两个过滤器。 这样就不需要在Content Browser的树视图中选择两个文件夹。

    这也扩展了资产的完整路径名，以获得很少的收益。 静态网格的 S_ 前缀只有两个字符，而 Meshes/ 是七个字符。
如果不这样做，也可以避免将静态网格或纹理放入 Materials 文件夹。

#### 2.7 非常大的资产集获得自己的文件夹布局：

这可以看作是对2.6的伪异常。

    有某些资产类型具有大量的相关文件，其中每个资产都有独特的用途。 最常见的两种是动画和音频资产。 如果你发现自己有15种资产属于一起，它们应该在一起。

    例如，跨多个字符共享的动画应该放在 Characters/Common/Animations 中，并且可能有子文件夹，例如 Locomotion 或 Cinematic。

    这不适用于纹理和材料等资产。 如果有大量的 Rocks ，岩石文件夹中有大量的纹理是很常见的，但是这些纹理通常只与少数特定的岩石有关，并且应该适当地命名。 即使这些纹理是材料库的一部分。

### 2.8 材料图书馆：

    如果您的项目使用了不属于任何资产子集的主材料、分层材料或任何形式的可重用材料或纹理，则这些资产应位于 Content/Project/MaterialLibrary 中。

    这样，所有“全局”材料都有一个存放的地方，而且很容易找到。

    这也使得在项目中强制执行“只使用重要实例”策略变得非常容易。 如果所有艺术家和资产都应该使用材料实例，那么应该存在的唯一常规材料资产就在这个文件夹中。 您可以很容易地通过在任何不是 MaterialLibrary 的文件夹中搜索基本材料来验证这一点。

    MaterialLibrary 不一定要由纯粹的材料组成。 共享的实用结构、材料功能和其他这种性质的东西应该存储在这里以及指定它们预期用途的文件夹中。 例如，通用噪声纹理应该位于 MaterialLibrary/Utility 中。

    任何测试或调试材料应在 MaterialLibrary/Debug 中。 这使得调试材料可以在发货前很容易地从项目中剥离出来，如果显示了引用错误，那么如果生产资产正在使用它们，这将非常明显。

### 2.9 不要存在空文件夹：

不应该有任何空文件夹。 他们把内容浏览器弄得乱七八糟。

如果发现内容浏览器有空文件夹无法删除，应执行以下操作：

    1. 一定要用源代码控制。
    2. 立即运行修复更新指导您的项目。
    3. 导航到磁盘上的文件夹并删除里面的资产。
    4. 关闭 Editor。
    5. 确保源控制状态是同步的(如果使用 Perforce ，则在内容目录上运行Reconcile Offline Work)。
    6. 打开编辑器。 确认一切仍然正常。 如果没有，请回复，找出问题所在，然后再试一次。
    7. 确保文件夹现在没有了。
    8. 提交对源控制的更改。

## 3.蓝图：

本节将集中讨论Blueprint类及其内部部分。样式规则符合自 Epic's Coding Standard。

### 3.1 编译：

    所有蓝图应以零警告和零错误进行编译。 您应该立即修复蓝图警告和错误，因为它们可以快速级联到非常可怕的意外行为。

    不要向源控制提交损坏的蓝图。 如果必须将它们存储在源控件上，则将它们搁置起来。

### 3.2 变量：

    variable 和 property 可以使用交换。

#### 3.2.1命名：

##### 3.2.1.1 名词：

    所有非布尔变量名必须是清晰、明确和描述性的名词。

##### 3.2.1.2 PascalCase：

    所有非布尔变量都应该是PascalCase的形式。

###### 3.2.1.2e 示例:

```
Score
Kills
TargetPlayer
Range
CrosshairColor
AbilityID
```
##### 3.2.1.3 布尔b前缀：

    所有的布尔值都应该用 PascalCase 命名，但以小写 b 为前缀。

    示例：使用 bDead 和 bEvil ，而不是 Dead 和 Evil 。

    UE4 蓝图编辑器默认不包括b。

##### 3.2.1.4 布尔名称：

###### 3.2.1.4.1 一般和独立状态信：

    如果可能的话，所有的布尔类型都应该被命名为描述性形容词，如果代表一般信息的话。 不包括将变量短语作为问题的单词，例如 Is 。 这是为功能保留的。

    示例：使用 bDead 和 bHostile，而不是 bIsDead 和 bIsHostile。

    尽量不要使用动词，如 bRunning。 动词往往会导致复杂的状态

###### 3.2.1.4.2 复杂状态信息：

    不要使用布尔表示复杂和/或依赖状态。 这使得状态添加和删除变得复杂，不再容易阅读。 使用枚举代替。

    例如：在定义武器时，如果武器不能同时重装和装备，不要使用 bReloading 和 bEquipping 。 定义一个名为 Ewaponstate 的枚举，并使用这个类型的变量名为 EWeaponState 。 这使得在武器上增加新的状态更加容易。

##### 3.2.1.5 考虑到上下文：

所有变量名都不能与它们的上下文冗余，因为蓝图中的所有变量引用都将始终具有上下文。

###### 3.2.1.5e 示例:

    考虑一个名为 BP_PlayerCharacter 的蓝图。

1. Bad：
```
    PlayerScore
    PlayerKills
    MyTargetPlayer
    MyCharacterName
    CharacterSkills
    ChosenCharacterSkin
```

2. Good:
```
   Score
   Kills
   TargetPlayer
   Name
   Skills
   Skin
```
##### 3.2.1.6 不包括原子类型名称：

    原子或原始变量是以最简单的形式表示数据的变量，如布尔值、整数、浮点数和枚举。

    字符串和向量在处理蓝图时被认为是原子的，但是它们在技术上不是原子的。

    虽然向量由三个浮点数组成，但向量通常可以作为一个整体进行操作，与旋转器相同。

    不要认为文本变量是原子的，它们秘密地隐藏了定位功能。 字符串的原子类型是String，而不是Text。

    原子变量的名称中不应该有它们的类型名称。

    示例: 使用 Score, Kills, and Description， 而不是 ScoreFloat, FloatKills, DescriptionString。

    这个规则的唯一例外是当一个变量表示要计数的“若干”的东西时，当使用没有变量类型的名称时，不容易读取。

    示例: 栅栏发生器需要生成 X 个柱子。 将 X 存储在 Num Posts 或 Posts 计数中，而不是 Posts ，因为 Posts 可能被读取为变量类型 Post 的数组。

##### 3.2.1.7 包括非原子类型的名称：

    非原子或复变量是将数据表示为原子变量集合的变量。 具有隐藏行为（如 Text 和Name）的结构、类、接口和原语都符合此规则。

    原子变量类型的数组是变量列表，而数组不会改变变量类型的'atomicness'。
    这些变量应该包括它们的类型名称，同时仍然考虑它们的上下文。

    如果类拥有一个复杂变量的实例，即。 如果 BP_PlayerCharacter 字符拥有BP_Hat，则应该将其存储为变量类型，就像没有任何名称修改一样。

    示例: 使用 Hat, Flag, and Ability 而不是 MyHat, MyFlag, and PlayerAbility。

    如果类不拥有复杂变量所表示的值，则应该使用名词和变量类型.

    示例：如果 BP_Turret 具有针对 BP_PlayerCharacter 字符的能力，则它应该将其目标存储为 TargetPlayer，就像在 BP_Turret 的上下文中一样，它应该清楚地表明它是对它不拥有的另一个复杂变量类型的引用。

##### 3.2.1.8 数组：

    数组遵循与上面相同的命名规则，但应命名为复数名词。

    示例：使用Targets, Hats, and EnemyPlayers, 而不是 TargetList, HatArray, EnemyPlayerArray。


#### 3.2.2 可编辑变量：

    为了配置蓝图的行为而安全地更改其值的所有变量都应标记为 Editable 的。

    相反，所有不安全更改或不应暴露给设计师的变量都不应被标记为可编辑，除非出于工程原因，变量必须标记为 Expose On Spawn。

    不要任意标记变量为 Editable 的。

##### 3.2.2.1 工具提示：

    所有包括那些标记为 Editable 的变量，以便它们可以被标记为 Expose On Spawn ，都应该在其 Tooltip 字段中有一个描述，该描述解释了更改此值如何影响蓝图的行为。

##### 3.2.2.2 滑块和价值范围：

    所有 Editable 都应该使用滑块和值范围，如果有一个变量则不应该设置。

    示例：生成栅栏柱子的蓝图可能有一个可编辑的变量，名为 PostsCount ，值为-1是没有意义的。 使用范围字段将0标记为最小值。

    如果在构建脚本中使用可编辑变量，则应该定义一个合理的滑块范围，这样人们就不会意外地给它分配一个大值，从而使编辑器崩溃。

    只有在已知值的界限时，才需要定义值域。 虽然滑块范围可以防止意外的大量输入，但未定义的值范围允许用户指定滑块范围之外的值，该值可能被认为是“危险的”，但仍然有效。

#### 3.2.3 Categories：

    如果一个类只有少量变量，则不需要类别。

    如果一个类有适量的变量（5-10），所有 Editable 变量都应该有一个非默认的类别分配。 一个常见的类别是 Config 。

    如果一个类有大量的变量，所有 Editable 变量都应该使用类别配置作为基类分类为子类别。不可编辑变量应分类为描述其用法的描述性类别。

```
您可以使用管道字符定义子类别。

```

示例：武器类变量集可以组织为：

```
|-- Config
|	|-- Animations
|	|-- Effects
|	|-- Audio
|	|-- Recoil
|	|-- Timings
|-- Animations
|-- State
|-- Visuals

```

#### 3.2.4 可变访问级别：

    在C++中，变量具有访问级别的概念。 公共意味着类之外的任何代码都可以访问变量。 受保护意味着只有类和任何子类可以在内部访问此变量。 私有意味着只有这个类，没有子类可以访问这个变量。

    蓝图目前没有定义的受保护访问的概念。

    将 Editable 变量视为公共变量。将不可编辑变量视为受保护变量。

##### 3.2.4.1 私有变量：

    除非已知变量只应在定义的类中访问，而不应在子类中访问，否则不要将变量标记为私有变量。 在变量能够被标记为 protected 之前，当您绝对知道要限制子类的使用时，保留私有。


#### 3.2.5 高级显示：

    如果变量应该是可编辑的，但通常是未触及的，请将其标记为 Advanced Display。 这使得变量隐藏，除非单击高级显示箭头

    要找到Advanced Display选项，它将在变量详细信息列表中列为高级显示变量。

#### 3.2.6 瞬态变量：

    瞬态变量是不需要保存和加载它们的值并且初始值为零或空的变量。 这对于引用到运行时才知道值的其他对象和参与者是有用的。 这使得编辑器无法保存对它的引用，并加快了蓝图类的保存和加载。

    正因为如此，所有瞬态变量都应该初始化为零或零。否则将导致难以调试的错误。

3.2.7 配置变量：

    不要使用 Config Variable 标志。这使得设计师更难控制蓝图行为。配置变量只能用于C中很少更改的变量。把它们看作 Advanced Advanced Display。

## 3.3 函数、事件和事件调度器:

    本节描述如何编写函数、事件和事件分派器。 除另有说明外，适用于事件，除非另有说明。

### 3.3.1 函数命名：

    函数、事件和事件调度器的命名至关重要。 仅基于名称，就可以对函数作出某些假设。 例如：

```
1. Is it a pure function?
2. Is it fetching state information?
3. Is it a handler?
4. Is it an RPC?
5. What is its purpose?

```
当适当命名函数时，这些问题和更多问题都可以得到回答。

##### 3.3.1.1 所有功能都应该是动词：

    所有函数和事件都执行某种形式的操作，无论是获取信息、计算数据还是导致某物爆炸。 因此，所有的函数都应该以动词开头。 只要有可能，它们都应该用现在时措辞。 他们也应该对他们正在做的事情有一些背景。

    在OnRep函数中，事件处理程序和事件分派器是此规则的例外。

1. Good examples:

```
1. Fire - Good example if in a Character / Weapon class, as it has context. Bad if in a Barrel / Grass / any ambiguous class.
2. Jump - Good example if in a Character class, otherwise, needs context.
3. Explode
4. ReceiveMessage
5. SortPlayerArray
6. GetArmOffset
7. GetCoordinates
8. UpdateTransforms
9. EnableBigHeadMode
10. IsEnemy - "Is" is a verb.

```

2. Bad examples:

```
1. Dead - Is Dead? Will deaden?
2. Rock
3. ProcessData - Ambiguous, these words mean nothing.
4. PlayerState - Nouns are ambiguous.
5. Color - Verb with no context, or ambiguous noun.

```

##### 3.3.1.2 属性 RepNotify 总是在 OnRep_Variable上：

    使用通知变量复制的所有函数都应该在OnRep_Variable。 这是由蓝图编辑器强制执行的。 如果你写了一个 然而，在 OnRep 函数上，当它暴露于Blueprint时，它也应该遵循这个约定。

##### 3.3.1.3 信息功能返回工具应该问问题

    当编写一个函数时，它不会改变或修改任何对象的状态，并且纯粹是为了获取信息、状态或计算一个是/否值，它应该问一个问题。 这也应该遵循 the verb rule 。

    这是极其重要的，就好像一个问题没有被问到，可以假设函数执行一个动作，并返回该动作是否成功。

1. Good examples:

```
1. IsDead
2. IsOnFire
3. IsAlive
4. IsSpeaking
5. IsHavingAnExistentialCrisis
6. IsVisible
7. HasWeapon - "Has" is a verb.
8. WasCharging - "Was" is past-tense of "be". Use "was" when referring to 'previous frame' or 'previous state'.
9. CanReload - "Can" is a verb.

```

2. Bad examples:

```
1. Fire - Is on fire? Will fire? Do fire?
2. OnFire - Can be confused with event dispatcher for firing.
3. Dead - Is dead? Will deaden?
4. Visibility - Is visible? Set visibility? A description of flying conditions?

```

##### 3.3.1.4 Event Handlers 和 Dispatchers 应该使用 On 开头：

    任何处理事件或分派事件的函数都应该以On开头，并继续遵循动词规则。 然而，如果过去的句子读得更好，动词可能会移到结尾。

    单词On的搭配不遵循动词规则。

    Handle 是不允许的。 使用 On 而不是 Handle，而其他框架可能更喜欢使用 Handle 而不是 On 。

1. Good examples:

```
1. OnDeath - Common collocation in games
2. OnPickup
3. OnReceiveMessage
4. OnMessageRecieved
5. OnTargetChanged
6. OnClick
7. OnLeave

```

2. Bad examples:

```
1. OnData
2. OnTarget
3. HandleMessage
4. HandleDeath

```

##### 3.3.1.5 远程程序呼叫应该以目标为前缀：

    每当创建RPC时，它都应该以Server、Client或Multicast作为前缀。 无例外。

    在前缀之后，遵循有关函数命名的所有其他规则。

1. Good examples：

```
1. ServerFireWeapon
2. ClientNotifyDeath
3. MulticastSpawnTracerEffect

```

2. Bad examples：

```
1. FireWeapon - Does not indicate its an RPC of some kind.
2. ServerClientBroadcast - Confusing.
3. AllNotifyDeath - Use Multicast, never All.
4. ClientWeapon - No verb, ambiguous.

```

#### 3.3.2 所有功能必须有返回节点：

    所有功能必须有返回节点，无异常。

    返回节点显式地注意到函数已完成其执行。 在一个蓝图可以充满 Sequence 、 ForLoopWithBreak 和反向重新路由节点的世界中，显式执行流程对于可读性、维护和更容易的调试非常重要。

    蓝图编译器能够跟踪执行流程，并将警告您，如果您使用返回节点时，您的代码中有一个分支具有未处理的返回或坏流。

    在类似的情况下，程序员可以在for循环完成后向 Sequence 节点添加引脚或添加逻辑，迭代可能会提前返回，这通常会导致代码流中的意外错误。 蓝图编译器的警告将立即提醒每个人这些问题。

#### 3.3.3 函数不应该超过50个节点：

    简单地说，任何功能都不应该有超过50个节点。 任何如此大的功能都应该分解为更小的功能，以便于可读性和易于维护。

    以下节点不计算在内，因为它们被认为不会增加函数复杂度：

```
1. Comment
2. Route
3. Cast
4. Getting a Variable
5. Breaking a Struct
6. Function Entry
7. Self

```

#### 3.3.4 所有公共职能都应该有描述：

    此规则更多地应用于公共面向或市场蓝图，这样其他人就可以更容易地导航和使用蓝图API。

    简单地说，任何具有访问特定对象的函数都应该填写其描述。

#### 3.3.5 所有自定义静态插件 BlueprintCallable 函数必须被插件名称分类：

    如果您的项目包含一个 static BlueprintCallable 用函数的插件，它们应该将其类别设置为插件的名称或插件名称的子集类别。

    例如，Zed Camera Interface 口或 Zed Camera Interface | Image Capturing。

### 3.4 蓝图图表:

    本节涵盖适用于所有蓝图的内容。

#### 3.4.1 没有意大利面条式的连线：

    连接线应该有明确的开始和结束。 你不应该在精神上解开连接线来理解一个图表。 以下许多章节都致力于减少意大利面。

#### 3.4.2 对齐连接线而不是节点：

    总是对齐连接线，而不是节点。 您不能总是控制节点上的大小和引脚位置，但您可以始终控制节点的位置，从而控制连接线。 直线提供清晰的线性流动。 歪歪扭扭的连接线坏得要命。 您可以通过使用带有选定BP节点的“直线连接”命令来理顺连接线。 热键：Q

1. Good example: 节点的顶部是交错的，以保持一个完美的直线白色执行线。

![Good](https://i.imgur.com/DNYxRqs.png)

2. Bad Example: 节点的顶部是对齐的，创建了一个扭曲的白色执行线。

![Bad](https://i.imgur.com/dzLXdAO.png)

3. Acceptable Example: 无论如何使用对齐工具，某些节点都可能不合作。 在这种情况下，尝试通过使节点更接近来最小化摆动。

![Acceptable](https://i.imgur.com/CPU5kxH.png)

#### 3.4.3 白色执行行是最优先的:

    如果您必须在理顺线性白色执行线或理顺某种类型的数据线之间做出决定，请始终理顺白色执行线。

#### 3.4.4 图表需要合理的Commend：

    节点块应该被包含在描述其高级行为的注释中。 虽然每个函数都应该被很好地命名，以便每个单独的节点易于阅读和理解，但对某一目的作出贡献的节点组应该在注释块中描述它们的目的。 如果一个函数没有多个节点块，并且很明显节点在函数的目标中服务于直接目的，那么它们就不需要被注释，因为函数名和描述应该就足够了。

#### 3.4.5 图表应在适当的地方处理Cast错误：

    如果一个函数或事件假设一个CAST总是成功的，那么如果CAST失败，它应该适当地报告逻辑上的失败。 这让其他人知道为什么“本来应该工作”的东西不能。 如果已知被转换的引用可能永远不会被转换，则函数还应该在失败的转换之后尝试一个优雅的恢复。

    这并不意味着每个Cast节点都应该处理其故障。 在许多情况下，特别是关于碰撞之类的事情的事件，预计执行流会悄悄地终止于失败的转换。

#### 3.4.6 图表不应该有任何摆动/松散/死节点：

    所有蓝图图中的所有节点都必须有目的。 您不应该在周围留下悬挂的蓝图节点，这些节点没有蓝图节点。

## 4. 静态网格体：

### 4.1 静态网格体 UVs：

    如果 Linter 报告了不好的 UVs ，而您似乎无法跟踪它，请在项目的 Saved/Logs 文件夹中打开结果的 .log 文件，以了解它失败的原因的确切细节。 我希望在未来的 Lint 报告中包含这些信息。

#### 4.1.1 所有网格体必须有UVs：

    很简单。 所有的网格，无论如何使用，都不应该缺少UV。

#### 4.1.2 所有网格体都不能有重叠的 UVs 为 Lightmaps：

    很简单。 所有网格体，无论如何使用，都应该具有有效的不重叠UVs。

### 4.2 LODs需要被正确的设置：

    主观检查每个项目的基础上，但作为一般规则，任何网格体可以看到在不同的距离应该有适当的LOD。

### 4.3 模块化无套接字资产应该干净地抓取到网格体：

    这是对每个资产的主观检查，但是任何模块化的无套接字资产都应该根据项目的网格设置干净地组合在一起。

    该项目是基于2个网格的功率，还是基于基础10网格。 然而，如果您正在为市场创建模块化的无套接字资产，Epic的要求是，当网格设置为10个单元或更大时，它们会干净地断裂。

### 4.4 所有网格体必须有碰撞：

    无论资产是否将用于级别中的碰撞，所有网格都应该定义适当的碰撞。 这有助于发动机的事情，如边界计算，遮挡和照明。 碰撞也应该形成良好的资产。

### 4.5 所有网格体应正确缩放：

    这是对每个项目的主观检查，但是所有资产都应该正确地缩放到他们的项目。 水平设计师或蓝图作者不应该需要调整网格的规模，以使他们在编辑器中确认。 引擎中的缩放网格应该被视为缩放覆盖，而不是缩放校正。

## 5. 粒子系统：

    本节将重点讨论粒子系统资产及其内部。

### 5.1 发射器命名：

    粒子系统中的所有发射器都应该被命名为描述性的东西，而不是留给他们的默认名称'ParticleEmitter'。

## 6. Levels / Maps:

### 6.1 没有 Error 或 Warning:

    所有级别都应加载零 errors 或 warnings。 如果有任何 errors 或 warnings 的级别加载，则应立即修复它们，以防止级联问题。

    您可以使用控制台命令“map check”在编辑器中的打开级别上运行map check”

    请注意：Linter在这方面比编辑器当前更严格，并将捕获编辑器将自己解决的加载错误。

### 6.2 构建照明：

    这是正常的发展过程中，水平偶尔没有照明建成。 当进行测试/内部/运输构建或任何要分发的构建时，应该始终构建照明。

### 6.3 没有玩家可见 Z-fighting：

    Levels 不应该有任何 z-fighting 在所有区域可见的球员。

### 6.4 市场具体规则:

    如果一个项目要在UE4市场上销售，它必须遵循这些规则

#### 6.4.1 概述Level：

    如果您的项目包含应该可视化或演示的资产，则必须在项目中包含包含名称“概述”的地图。

    这个概览图，如果它是可视化的资产，应该根据Epic的指导方针建立。
    
    示例, InteractionComponent_Overview。

#### 6.4.2 演示Level：

    如果您的项目包含应该演示的资产或附带某种教程，您必须在项目中有一个包含名称“演示”的地图”。 这个级别还应该包含以某种形式说明如何使用项目的文档。 有关如何做到这一点，请参阅Epic的内容示例项目。
    
    如果你的项目是一个游戏机械或其他形式的系统，而不是一个艺术包，这可以是相同的“概述”地图。
    
    示例, InteractionComponent_Overview_Demo, ExplosionKit_Demo。

## 7. Textures：

### 7.1 2维：

    所有的纹理，除了UI纹理，必须有尺寸的倍数为2。 纹理不必是正方形的。

    示例, 128x512, 1024x1024, 2048x1024, 1024x2048, 1x512。

### 7.2 纹理密度应均匀：

    所有纹理的大小都应该适合它们的标准用例。 适当的纹理密度因项目而异，但该项目中的所有纹理都应该具有一致的密度。

    例如，如果一个项目的纹理密度是每1个单元8个像素，那么打算应用于100x100单元立方体的纹理应该是1024x1024，因为这是与项目纹理密度匹配的最接近的2的功率。

### 7.3 纹理不应大于8192：
    
    没有纹理应该有一个尺寸超过8192的大小，除非你有一个非常明确的理由这样做。 通常，使用这么大的纹理只是浪费资源。

### 7.4 应正确分组纹理：
    
    每个纹理都有一个用于 LODing 的纹理组属性，并且应该根据其使用来正确设置。 例如，所有UI纹理都应该属于UI纹理组。


