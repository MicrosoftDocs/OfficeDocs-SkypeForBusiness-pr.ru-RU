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
ms.openlocfilehash: 91b69eedcdb58d5a7cdb5cf96c1b98e7a6eedbd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Создание или изменение правила нормализации вручную в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-22_

Выполните следующие действия, чтобы создать или изменить правило нормализации вручную. Если вы хотите создать или изменить правило нормализации с помощью построения правила нормализации в панели управления Lync Server, ознакомьтесь со статьей [Создание или изменение правила нормализации с помощью построения правила нормализации в Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

<div>

## <a name="to-define-a-normalization-rule-manually"></a>Определение правила нормализации вручную

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Необязательно Выполните действия, описанные в статье [Создание абонентской группы в Lync server 2013](lync-server-2013-create-a-dial-plan.md) или [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  В разделе **New Normalization Rule** (Создать правило нормализации) или **Edit Normalization Rule** (Изменить правило нормализации) в поле **Имя** введите шаблон нормализуемого номера (например, задайте имя правила нормализации **5DigitExtension**).

5.  (Дополнительно). В поле **Описание** введите описание правила нормализации (например, "Преобразование расширений из 5 цифр").

6.  В разделе **Build a Normalization Rule** (Создание правила нормализации) нажмите кнопку **Изменить**.

7.  В разделе **Type a Regular Expression** (Введите регулярное выражение) введите следующие данные.
    
      - В поле **Match this pattern** (Соответствие этому шаблону) укажите шаблон, который требуется использовать для сопоставления набираемых номеров.
    
      - В поле **Translation rule** (Правило преобразования) укажите шаблон для формата преобразуемых номеров E.164.
    
    Например, если ввести **^\\({7}d) $** в поле **найти** , а затем **+ 1425 $1** в **правиле трансляции**, то правило нормализует 5550100 до + 14255550100.

8.  (Дополнительно). Если в результате применения правила нормализации получается внутренний номер телефона организации, выберите **Internal extension** (Внутренний добавочный номер).

9.  (Дополнительно). Введите номер для проверки правила нормализации, а затем нажмите кнопку **Перейти**. Результаты проверки отображаются в разделе **Enter a number to test** (Введите номер телефона для проверки).
    
    <div>
    

    > [!NOTE]  
    > Можно сохранить правило нормализации, которое еще не прошло проверку, а затем изменить его настройки. Дополнительные сведения см <A href="lync-server-2013-test-voice-routing.md">в статье Проверка маршрутизации голосовой связи в Lync Server 2013</A>.

    
    </div>

10. Нажмите кнопку **ОК**, чтобы сохранить правило нормализации.

11. Нажмите кнопку **ОК**, чтобы сохранить абонентскую группу.

12. На странице **Абонентская группа**, нажмите кнопку **Зафиксировать**, а затем **Commit all** (Фиксировать все).
    
    <div>
    

    > [!NOTE]  
    > Каждый раз при создании или изменении правила нормализации следует запускать команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации. Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение правила нормализации с помощью построения правила нормализации в Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Проверка маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

