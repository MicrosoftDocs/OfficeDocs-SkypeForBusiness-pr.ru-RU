---
title: 'Lync Server 2013: Настройка нового доверенного сервера приложений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Настройка нового доверенного сервера приложений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Надежное приложение — это приложение, основанное на API Microsoft Lync 2013 Server (УКМА 3,0), которое является надежным для Windows. Подробнее об УКМА приложениях можно найти в [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)разделе "управляемая унифицированная связь API 3,0 Core SDK".

Сведения о настройке Microsoft Outlook Web Access (OWA) и Lync Server 2013 можно найти в разделе "Настройка Outlook Web App и Lync Server 2010" в документации по Microsoft Exchange Server 2013.

Чтобы успешно публиковать, включать и отключать топологию при добавлении или удалении роли сервера, вы должны войти в систему как пользователь, который является членом группы администраторов Рткуниверсалсерверадминс и domain. Кроме того, можно делегировать права администратора и права на Добавление ролей сервера. Дополнительные сведения можно найти [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию. Для других изменений конфигурации требуется только членство в группе Рткуниверсалсерверадминс.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Настройка доверенного сервера приложений

1.  Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.

2.  Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.

3.  Выберите пункт **топология скачивания из существующего развертывания**и нажмите кнопку **ОК**.

4.  В диалоговом окне **Сохранить топологию как** выберите нужный файл в построителе топологии, а затем нажмите кнопку **сохранить**.

5.  На левой панели щелкните правой кнопкой мыши **Доверенные серверы приложений**и выберите команду **создать доверенный пул приложений**.

6.  Введите **полное доменное имя пула** для доверенного пула приложений, укажите, будет ли он одним или несколькими серверами, и нажмите кнопку **Далее**.

7.  На странице **Выбор следующего прыжка** в списке выберите пул внешних интерфейсов Lync Server 2013.

8.  Нажмите **Готово**.

9.  Выберите верхний узел **Lync Server 2013**, а затем в меню **действия** выберите пункт **топология публикации**.
    
    **Надежное приложение пула приложений** должно быть успешно создано и связано с правильным пулом переднего плана.

</div>

</div>

<span> </span>

</div>

</div>

</div>

