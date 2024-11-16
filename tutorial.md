#　水族館をつくろう！

## {Introduction @unplugged}

**海の生き物たちのために、居心地のいい素敵な水族館をつくってみよう！**

## Step1

**トライデント**を使って水族館が作成されるようにしましょう！
``||player.次のアイテムが使われた時||``を選択し、アイテムの種類で**トライデント**を選びましょう。


```blocks
player.onItemInteracted(IRON_SHOVEL, function() {})
```
を選択し、アイテムの種類で**トライデント**を選びましょう。

## Step2

水槽のガラス部分を作成するために``||blocks.ブロックを並べる||``をコードに追加しましょう。

```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GRASS,
    pos(0,0,0),
    pos(0,0,0),
    FillOperation.Replace
    )
    })
```

## Step3

8 x 8 x 20 のスペースがあれば海の生き物たちにとっては十分でしょう。``||blocks.ブロックを並べる||``の中の**範囲の始まり**の位置を**~5 ~0 ~-10**
に設定し**範囲の終わり**の位置を**~12 ~7 ~10**に設定しましょう。魚たちと一緒に水の中で泳ぐことにならないように、始まりの位置には 5 と 12 を使います。
```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GLASS,
    pos(5,0,-10),
    pos(12,7,10),
    FillOperation.Replace
    )
    })
```

## Step4

次に水槽に水を追加するにも``||blocks.ブロックを並べる||``を使用します。新たにコードに追加し、ブロックの種類には**水**を選びましょう。

```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GLASS,
    pos(5,0,-10),
    pos(12,7,10),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    pos(0,0,0),
    pos(0,0,0),
    FillOperation.Replace
    )
    })
```

## Step5

水槽の中を水でいっぱいにします。``||blocks.ブロックを並べる||``の中の**範囲の始まり**の位置を**~6 ~1 ~-9**
に設定し**範囲の終わり**の位置を**~11 ~6 ~9**に設定しましょう。

```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GLASS,
    pos(5,0,-10),
    pos(12,7,10),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    pos(6,1,-9),
    pos(11,6,9),
    FillOperation.Replace
    )
    })
```

## Step6

これで海の生き物たちを迎え入れる準備ができました！たくさんの魚たちを迎え入れたいので``||loops.ループ||``のコマンドを使います。コードに追加しましょう。

```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GLASS,
    pos(5,0,-10),
    pos(12,7,10),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    pos(6,1,-9),
    pos(11,6,9),
    FillOperation.Replace
    )
    for (let index = 0; index < 4; index++){
    }
    })
```

## Step7

魚を迎え入れましょう。まずは**イルカ**を迎え入れます。``||mobs: 生き物をスポーンさせる||``を``||loops.ループ||``の中に配置して、生き物の種類に**イルカ**を選びましょう。

```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GLASS,
    pos(5,0,-10),
    pos(12,7,10),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    pos(6,1,-9),
    pos(11,6,9),
    FillOperation.Replace
    )
    for (let index = 0; index < 4; index++){
    mobs.spawn(DOLPHIN, pos(0,0,0)
    ))
    }
    })
```

## Step8

次に水槽の中で魚がランダムに出現するようにします。``||positions:　ランダムな座標||``を``||mobs: スポーンさせる||``の中に入れて、水がある場所と同じ場所にスポーンするように**範囲の始まり**の位置を**~6 ~1 ~-9**
に設定し**範囲の終わり**の位置を**~11 ~6 ~9**に設定しましょう。

```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GLASS,
    pos(5,0,-10),
    pos(12,7,10),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    pos(6,1,-9),
    pos(11,6,9),
    FillOperation.Replace
    )
    for (let index = 0; index < 4; index++){
    mobs.spawn(DOLPHIN, randpos(
    pos(6,1,-9),
    pos(11,6,9),
    ))
    }
    })
```

## Step9

同じようにして、好きな魚を水槽に迎え入れましょう。マインクラフトの世界には**鮭**や**熱帯魚**、**ウミガメ**など様々な生き物が存在しています。

```blocks
player.onItemInteracted(TRIDENT, function() {
    blocks.fill(
    GLASS,
    pos(5,0,-10),
    pos(12,7,10),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    pos(6,1,-9),
    pos(11,6,9),
    FillOperation.Replace
    )
    for (let index = 0; index < 4; index++){
    mobs.spawn(DOLPHIN, randpos(
    pos(6,1,-9),
    pos(11,6,9),
    ))
    mobs.spawn(SEA_TURTLE, randpos(
    pos(6,1,-9),
    pos(11,6,9),
    ))
    mobs.spawn(TROPICAL_FISH, randpos(
    pos(6,1,-9),
    pos(11,6,9),
    ))
    }
    })
```
