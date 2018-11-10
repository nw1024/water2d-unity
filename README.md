# Shader Based Motion

Adding \_Speed parameter to shader to replace script based motion and simplify the asset.

# New Method

    _Speed("Speed", Range(-2,2)) = 1.0 
    ...
    float  _Speed;
    ...

    half4 frag (vertexOutput i) : SV_Target
    {
        fixed timescroll = _Speed * _Time;
        half4 bump = tex2D(_MainTex, i.uvmain + fixed2(timescroll,0));
        ...
    
# Old Method

    public class Water2DScript : MonoBehaviour
    {
    ...
    void LateUpdate()
    {
        Vector2 scroll = Time.deltaTime * speed;
        mat.mainTextureOffset += scroll;
    }

Original readme:

# 2D Water surface in Unity3D

![screenshot](screenshot.gif)

## Description

A 2D water surface that will deform what is "underwater".

More details in [my blog post](http://dmayance.com/water-surface-2d-unity/).

Made with Unity 5.4.3f1 but should work on all Unity 5 versions.

*Not enough tested on mobile and not tested at all on consoles*

## Usage

1. Clone this repository or download the latest [release package available](https://github.com/valryon/water2d-unity/releases).

2. Add the "Water2D Surface" prefab in your scene. This is now your water.

3. Tweak the sprite order/layer of the surface

4. Add a `WaterReflectableScript` to any object you want to be reflected in the water

Enjoy! You can also simply place sprites under water using sprite layers/order.

## Credits

Demo assets made by the [Superpower team](https://github.com/sparklinlabs/superpowers-asset-packs).
