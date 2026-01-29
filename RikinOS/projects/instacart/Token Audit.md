I'm gonna do a deep dive into Tokens, and get an understanding of how the propagate in our system. The way I wanna tackle it is as follows:

Understand Core Token Sets and how they Propagate:
- Color
- Typography
- Size / Shape
- Spacing
- Opacitiy

These are foundation level that propagate through levels of tokens
```kotlin
![[Token Audit Canvas.canvas]]// an example being that semantic tokens can inehrit from base / foundation etc.
val Background = SystemGrayscale80
```

Then we can work around the levels of tokens a bit more, like our Component Level tokens.

Starting With Colors:

Classes to Look At:

foundation:
`BaseColors`
`ColorSpec`
`SemanticColors`
`BrushSpec`
`ColorExtensions`

core:
`Colors`
`CustomerColorSpecs`


This is essentially the guts of foundation
```kotlin
private object DefaultBaseColors : BaseColors {  
    override val systemGrayscale99: Color  
        get() = SystemGrayscale99  
    override val systemGrayscale90: Color  
        get() = SystemGrayscale90  
    override val systemGrayscale80: Color  
        get() = SystemGrayscale80  
    override val systemGrayscale60: Color  
        get() = SystemGrayscale60  
    override val systemGrayscale40: Color  
        get() = SystemGrayscale40  
    override val systemGrayscale30: Color  
        get() = SystemGrayscale30  
    override val systemGrayscale20: Color  
        get() = SystemGrayscale20  
    override val systemGrayscale10: Color  
        get() = SystemGrayscale10  
    override val systemGrayscale00: Color  
        get() = SystemGrayscale00  
    override val systemSuccessRegular: Color  
        get() = SystemSuccessRegular  
    override val systemSuccessDark: Color  
        get() = SystemSuccessDark  
    override val systemSuccessExtraDark: Color  
        get() = SystemSuccessExtraDark  
    override val systemSuccessLight: Color  
        get() = SystemSuccessLight  
    override val systemDetrimentalRegular: Color  
        get() = SystemDetrimentalRegular  
    override val systemDetrimentalDark: Color  
        get() = SystemDetrimentalDark  
    override val systemDetrimentalExtraDark: Color  
        get() = SystemDetrimentalExtraDark  
    override val systemDetrimentalLight: Color  
        get() = SystemDetrimentalLight  
    override val systemFeedbackAlertLight: Color  
        get() = SystemFeedbackAlertLight  
    override val systemFeedbackAlertRegular: Color  
        get() = SystemFeedbackAlertRegular  
    override val brandPrimaryRegular: Color  
        get() = BrandPrimaryRegular  
    override val brandPrimaryDark: Color  
        get() = BrandPrimaryDark  
    override val brandPrimaryExtraDark: Color  
        get() = BrandPrimaryExtraDark  
    override val brandPrimaryLight: Color  
        get() = BrandPrimaryLight  
    override val brandSecondaryRegular: Color  
        get() = BrandSecondaryRegular  
    override val brandSecondaryDark: Color  
        get() = BrandSecondaryDark  
    override val brandSecondaryExtraDark: Color  
        get() = BrandSecondaryExtraDark  
    override val brandSecondaryLight: Color  
        get() = BrandSecondaryLight  
    override val brandTertiaryRegular: Color  
        get() = BrandTertiaryRegular  
    override val brandTertiaryLight: Color  
        get() = BrandTertiaryLight  
    override val brandTertiaryDark: Color  
        get() = BrandTertiaryDark  
    override val brandHighlightRegular: Color  
        get() = BrandHighlightRegular  
    override val brandHighlightDark: Color  
        get() = BrandHighlightDark  
    override val brandHighlightLight: Color  
        get() = BrandHighlightLight  
    override val brandMaxLight: Color  
        get() = BrandMaxLight  
    override val brandMaxDark: Color  
        get() = BrandMaxDark  
    override val backgroundColor: Color  
        get() = SystemGrayscale00  
    override val surfaceColor: Color  
        get() = SystemGrayscale00  
    override val defaultColor: Color  
        get() = SystemGrayscale80  
}
```

```kotlin
@Immutable  
data class Colors(  
    override val systemGrayscale99: Color = SystemGrayscale99,  
    override val systemGrayscale90: Color = SystemGrayscale90,  
    override val systemGrayscale80: Color = SystemGrayscale80,  
    override val systemGrayscale60: Color = SystemGrayscale60,  
    override val systemGrayscale40: Color = SystemGrayscale40,  
    override val systemGrayscale30: Color = SystemGrayscale30,  
    override val systemGrayscale20: Color = SystemGrayscale20,  
    override val systemGrayscale10: Color = SystemGrayscale10,  
    override val systemGrayscale00: Color = SystemGrayscale00,  
  
    override val systemSuccessRegular: Color = SystemSuccessRegular,  
    override val systemSuccessDark: Color = SystemSuccessDark,  
    override val systemSuccessExtraDark: Color = SystemSuccessExtraDark,  
    override val systemSuccessLight: Color = SystemSuccessLight,  
  
    override val systemDetrimentalRegular: Color = SystemDetrimentalRegular,  
    override val systemDetrimentalDark: Color = SystemDetrimentalDark,  
    override val systemDetrimentalExtraDark: Color = SystemDetrimentalExtraDark,  
    override val systemDetrimentalLight: Color = SystemDetrimentalLight,  
  
    override val systemFeedbackAlertRegular: Color = SystemFeedbackAlertRegular,  
    override val systemFeedbackAlertLight: Color = SystemFeedbackAlertLight,  
  
    override val brandPrimaryRegular: Color = BrandPrimaryRegular,  
    override val brandPrimaryDark: Color = BrandPrimaryDark,  
    override val brandPrimaryExtraDark: Color = BrandPrimaryExtraDark,  
    override val brandPrimaryLight: Color = BrandPrimaryLight,  
  
    override val brandSecondaryRegular: Color = BrandSecondaryRegular,  
    override val brandSecondaryDark: Color = BrandSecondaryDark,  
    override val brandSecondaryExtraDark: Color = BrandSecondaryExtraDark,  
    override val brandSecondaryLight: Color = BrandSecondaryLight,  
  
    override val brandTertiaryRegular: Color = BrandTertiaryRegular,  
    override val brandTertiaryLight: Color = BrandTertiaryLight,  
    override val brandTertiaryDark: Color = BrandTertiaryDark,  
  
    override val brandHighlightRegular: Color = BrandHighlightRegular,  
    override val brandHighlightDark: Color = BrandHighlightDark,  
    override val brandHighlightLight: Color = BrandHighlightLight,  
  
    override val brandMaxLight: Color = BrandMaxLight,  
    override val brandMaxDark: Color = BrandMaxDark,  
  
    override val backgroundColor: Color = SystemGrayscale00,  
    override val surfaceColor: Color = SystemGrayscale00,  
    override val defaultColor: Color = SystemGrayscale80,  
  
    val brandPromotionalRegular: Color = LegacyColors.BrandPromotionalRegular,  
    val brandPromotionalDark: Color = LegacyColors.BrandPromotionalDark,  
    val brandPromotionalLight: Color = LegacyColors.BrandPromotionalLight,  
  
    val brandLoyaltyRegular: Color = BrandLoyaltyRegular,  
    val brandLoyaltyDark: Color = BrandLoyaltyDark,  
    val brandLoyaltyLight: Color = BrandLoyaltyLight,  
  
    val brandExpressRegular: Color = BrandExpressRegular,  
    val brandExpressDark: Color = BrandExpressDark,  
    val brandExpressExtraDark: Color = BrandExpressExtraDark,  
    val brandExpressLight: Color = BrandExpressLight,  
  
    val brandPlusExtraLight: Color = BrandPlus10,  
    val brandPlusLight: Color = BrandPlus40,  
    val brandPlusRegular: Color = BrandPlus50,  
    val brandPlusDark: Color = BrandPlus60,  
    val brandPlusExtraDark: Color = BrandPlus70,  
) : BaseColors {  
    companion object {  
        val Default = Colors()  
    }}
```

How do we typically access these colors? Typically though color spec OR the theme.

```kotlin
ColorSpec.BrandPrimaryRegular.value() == BaseTheme.colors.brandPrimaryRegular

// Customer Specific Colors get added to a companion object in core
// CustomerColorSpecs.kt
ColorSpec.BrandLoyaltyRegular.value() == Theme.colors.brandLoyalyRegular

```

One thing I am noticing here is that for colors, we don't have the primitive colors defined, our lowest level is SystemGrayscaleX, BrandXX, SystemFeedback, SystemDetrimental. But we also sort of keep semantic ones `background` `default`, etc.

We are also missing some color tokens (Brand_ExtraLight)

---

