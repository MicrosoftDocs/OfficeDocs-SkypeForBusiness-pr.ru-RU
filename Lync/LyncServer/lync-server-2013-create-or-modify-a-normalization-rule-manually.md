---
title: 'Lync Server 2013: создание или изменение правила нормализации вручную'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Создание или изменение правила нормализации вручную в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-22_

Если вы хотите создать или изменить правило нормализации вручную, выполните указанные ниже действия. Если вы хотите создать или изменить правило нормализации с помощью построения правила нормализации на панели управления Lync Server, ознакомьтесь со сведениями [Создание и изменение правила нормализации в Lync server 2013 с помощью сборки](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)правила нормализации.

<div>

## <a name="to-define-a-normalization-rule-manually"></a>Определение правила нормализации вручную

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Необязательно Выполните действия, описанные в статье [Создание абонентской группы в Lync server 2013](lync-server-2013-create-a-dial-plan.md) или [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  В разделе **создания** или **редактирования правила нормализации** в поле **Имя** введите имя, описывающее нормализуемый числовой шаблон (например, **5DigitExtension**).

5.  В поле **Описание** введите описание правила нормализации (например, "Преобразование пятизначных добавочных номеров") (не обязательно).

6.  В разделе **Построение правила нормализации** нажмите кнопку **Изменить**.

7.  В разделе **Введите регулярное выражение** введите следующие данные.
    
      - В поле **Сопоставить этот шаблон** укажите шаблон, которому должен соответствовать набираемый телефонный номер.
    
      - В поле **Правило трансляции** укажите шаблон для формата преобразуемых телефонных номеров E.164.
    
    Например, при вводе **\\^ (d{7}) $** в соответствии с **этим шаблоном** и **+ 1425 $1** в **правиле перевода**, правило нормализует 5550100 в + 14255550100.

8.  Если в результате применения правила нормализации получается внутренний телефонный номер организации, выберите **Внутреннее расширение** (не обязательно).

9.  Введите номер для проверки правила нормализации, затем нажмите кнопку **Перейти** (необязательно). Результаты проверки отображаются под полем **Введите номер телефона для проверки**.
    
    <div>
    

    > [!NOTE]  
    > Вы можете сохранить правило нормализации, которое еще не прошло тест, а затем настроить его позже. Подробные сведения можно найти <A href="lync-server-2013-test-voice-routing.md">в разделе Проверка маршрутизации голосовой связи в Lync Server 2013</A>.

    
    </div>

10. Нажмите кнопку **ОК** для сохранения правила нормализации.

11. Нажмите кнопку **ОК** для сохранения абонентской группы.

12. На странице **Абонентская группа** нажмите кнопку **Сохранить**, затем **Сохранить все**.
    
    <div>
    

    > [!NOTE]  
    > Каждый раз, когда вы создаете или изменяете правило нормализации, необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать изменение конфигурации. Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение правила нормализации с помощью сборки правила нормализации в Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Тестирование голосовой маршрутизации в Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

