# 菜谱推荐服务 How To Cook

基于MCP协议的AI菜谱推荐服务器，提供菜谱查询、分类筛选、智能膳食规划和每日菜单推荐功能。
An AI recipe recommendation server based on the MCP protocol, providing functions such as recipe query, classification filtering, intelligent dietary planning, and daily menu recommendation.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| mcp_howtocook_getAllRecipes | 获取所有菜谱 |
| mcp_howtocook_getRecipesByCategory | 根据分类查询菜谱，可选分类有: 水产, 早餐, 调料, 甜品, 饮品, 荤菜, 半成品加工, 汤, 主食, 素菜 |
| mcp_howtocook_recommendMeals | 根据用户的忌口、过敏原、人数智能推荐菜谱，创建一周的膳食计划以及大致的购物清单 |
| mcp_howtocook_whatToEat | 不知道吃什么？根据人数直接推荐适合的菜品组合 |
| mcp_howtocook_getRecipeById | 根据菜谱名称或ID查询指定菜谱的完整详情，包括食材、步骤等 |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659566595](https://mcp.xiaobenyang.com/inspector/1777316659566595)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659566595](https://mcp.xiaobenyang.com/inspector/1777316659566595)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "菜谱推荐服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659566595/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "菜谱推荐服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659566595/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "菜谱推荐服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659566595",
          },
          "transport": "stdio"
        }
      }
}

```
