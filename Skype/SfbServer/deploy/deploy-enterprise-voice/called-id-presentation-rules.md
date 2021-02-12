---
title: Create or modify a translation rule for called ID presentation in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: Сводка. Узнайте, как определить правило трансляции с помощью средства создания правила трансляции в Skype для бизнеса Server.
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804199"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Create or modify a translation rule for called ID presentation in Skype for Business Server

**Сводка:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.

Выполните следующие действия, чтобы определить правило трансляции, введите  набор значений в средстве создания правила трансляции и включив панель управления Skype для бизнеса Server для создания соответствующего шаблона и правила трансляции. В качестве альтернативного варианта можно задать шаблон поиска соответствия и правило преобразования вручную с помощью регулярного выражения. Дополнительные сведения см. в разделе [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)

1. Откройте панель управления Skype для бизнеса Server.

2. To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.

3. На странице **New Translation Rule** (Создание правила преобразования) или **Edit Translation Rule** (Изменение правила преобразования) в поле **Name** (Имя) введите описательное имя правила преобразования.

4. (Необязательно) В **описании** введите описание правила трансляции, например международного телефонного набора (US International).

5. В разделе **Build a Translation Rule** (Создание правила преобразования) введите следующие значения:

   - **Начальные цифры:**(Необязательно) Укажите начальные цифры чисел, которые должны соответствовать шаблону. Например, введите +в это поле для совпадения чисел в формате E.164 (которые начинаются с +).

   - **Длина:** укажите количество цифр в шаблоне совпадения и укажите, должен ли шаблон точно соответствовать номерам этой длины, по крайней мере этой длины или любой длины. Например, введите 11 и selectAt least в выпадаемом списке для совпадения номеров длиной не менее 11 цифр.

   - **Цифры, которые необходимо** удалить: (необязательно) Укажите количество начальных цифр, которые необходимо удалить. Например, введите 1, чтобы вывести +из начала номера.

   - **Цифры для добавления:**(Необязательно) Укажите цифры, которые необходимо добавить в преобразуемую цифру. Например, введите 011, если вы хотите, чтобы при применении правила к переведенным номерам был приложен номер 011.

     Значения, вводимые в этих полях, отражаются в полях **Pattern to match** (Шаблон для поиска соответствия) и **Translation rule** (Правило преобразования). Например, если вы ввели значения, показанные в предыдущем примере, в поле **Pattern to match** (Шаблон для поиска соответствия) будет добавлено следующее регулярное выражение:

     ^\+(\d {9} \d+)$

     Поле **Translation rule** (Правило преобразования) задает шаблон для формата преобразованных номеров. Этот шаблон состоит из 2 частей:

   - Значение (например, $1), которое представляет число цифр в шаблоне соответствия

   - Значение, добавляемое перед номером, которое вводится в поле **Digits to add** (Число добавляемых цифр) (необязательно)

     Для значений предыдущего примера в поле Translation rule (Правило преобразования) будет отображаться **011$1**.

     После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.

6. Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.

7. Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.

8. На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).

   > [!NOTE]
   > Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Commit all** (Сохранить все), чтобы опубликовать изменение конфигурации. For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.

### <a name="to-define-a-translation-rule-manually"></a>Определение правила преобразования вручную

1. Открытие панели управления Skype для бизнеса Server

2. To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.

3. В поле **Имя** на странице **Создание правила преобразования** или  **Изменение правила преобразования** введите имя, описывающее шаблон номера для преобразования.

4. (Необязательно) В **описании** введите описание правила трансляции, например для международного телефонного набора (US International).

5. Внизу раздела **Построение правила преобразования** нажмите кнопку **Правка**.

6. В диалоговом окне **Ввод регулярных выражений** введите следующее.

   - В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.

   - В поле **Правило преобразования** укажите шаблон для формата преобразованных номеров.

     Например, если ввести ^ (\d \d+)$ в соответствие этому шаблону и 011$1 в правиле трансляции, правило переведет \+ {9} +441235551010 в 011441235551010.  

7. Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.

8. Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.

9. На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).

    > [!NOTE]
    > Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Commit all** (Сохранить все), чтобы опубликовать изменение конфигурации. For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.

## <a name="see-also"></a>См. также

[Настройка магистрали с обходом сервера-посредника в Skype для бизнеса Server](configure-trunk-with-media-bypass.md)

[Настройка магистрали без обхода сервера-посредника в Skype для бизнеса Server](configure-trunk-without-media-bypass.md)

[Публикация ожидающих изменений в конфигурации маршрутации голосовой почты в Skype для бизнеса](voice-route-config-changes.md)

[Развертывание обхода сервера-посредника в Skype для бизнеса Server](deploy-media-bypass.md)

