---
title: Настройка сервера-посредника
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82da1720cab2e6895c53565da17c9411faabdfbd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Настройка сервера-посредника

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

В этой процедуре описываются действия по настройке пула Lync Server 2013 для использования сервера-посредника Lync Server 2013 вместо устаревшего сервера Office Communications Server 2007 R2.

Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо выполнить вход в качестве члена групп RTCUniversalServerAdmins и "Администраторы домена". Кроме того можно делегировать надлежащие права и разрешения администратора для добавления ролей сервера. Дополнительные сведения см. в разделе "Делегирование разрешений на установку" в документации по развертыванию сервера Standard Edition или сервера Enterprise Edition. Для всех остальных изменений конфигурации требуется только членство в группе RTCUniversalServerAdmins.

<div>


> [!NOTE]  
> Последние сведения о поиске подходящих шлюзов PSTN, IP-УАТС и магистрали SIP, работающих с Lync Server 2013, можно найти в статье "Microsoft Unified Communications Open Communications Program" <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Чтобы настроить сервер-посредник с помощью построителя топологии

1.  Откройте существующую топологию в окне построителя топологий.

2.  На левой панели перейдите к пункту **Шлюзы ТСОП**.

3.  Щелкните правой кнопкой мыши **Шлюзы ТСОП**, затем щелкните **Создать шлюз IP/ТСОП**.

4.  Заполните страницу **Определение нового шлюза IP/ТСОП**, указав приведенные ниже сведения.
    
      - Введите полное доменное имя или IP-адрес шлюза. Полное доменное имя шлюза необходимо, если шлюз использует протокол TLS.
    
      - Примите значение по умолчанию для параметра **Порт прослушивания для шлюза IP/ТСОП** или введите новый порт прослушивания.
    
      - Определите значение параметра **Транспортный протокол SIP**.

5.  На левой панели перейдите в раздел **Интерфейсный пул Enterprise Edition** или **Сервер Standard Edition**.

6.  Щелкните правой кнопкой мыши соответствующий пул, а затем выберите **Изменить свойства**.

7.  В разделе **Сервер-посредник** определите значение параметра **Порты прослушивания**.

8.  Затем сопоставьте новый созданный шлюз ТСОП, выбрав его и нажав кнопку **Добавить**.

9.  В **построителе топологий** выберите узел верхнего уровня **Lync Server**.

10. В меню **Действие** выберите пункт **Опубликовать топологию**, затем нажмите кнопку **Далее**.

11. По завершении работы **мастера публикации** нажмите кнопку **Готово**, чтобы закрыть мастер.

<div>


> [!NOTE]  
> Важно выполнить следующий раздел, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">изменить маршруты голосовой связи для использования нового сервера-посредника Lync server 2013</A> , чтобы убедиться, что маршруты голосовой связи указывают на правильный сервер-посредник.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

