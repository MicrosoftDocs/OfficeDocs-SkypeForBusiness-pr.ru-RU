---
title: 'Lync Server 2013: Просмотр обновлений программного обеспечения для устройств в вашей организации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Просмотр обновлений программного обеспечения для устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

В Lync Server 2013 вы используете веб-службу обновления устройств для просмотра обновлений программного обеспечения для устройств организации и управления ими. Эти обновления доступны на веб-сайте службы поддержки Майкрософт по адресу [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)CAB (CAB-файлов). Загрузив CAB-файл, выполните командлет **Import — ксдевицеупдате** , чтобы импортировать правила обновления устройства из файла CAB. Дополнительные сведения о командлете **Import-ксдевицеупдате** можно найти в документации [Import-Ксдевицеупдате](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) в командной консоли Lync Server Management Shell.

<div>


> [!TIP]  
> Перед развертыванием нового обновления в вашей организации убедитесь, что оно правильно работает на тестовом устройстве.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Просмотр обновлений программного обеспечения для устройств UC

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Скачайте CAB-файл в папку [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)на компьютере Lync Server 2013 (например, C:\\Updates\\. cab) на сайте службы поддержки Майкрософт по адресу.

3.  Импортируйте правила обновления устройства из файла C:\\Updates\\укупдатес. cab, выполнив один из следующих командлетов:
    
      - Если CAB-файл находится на том же компьютере, что и служба, для которой выполняется обновление (Service: Redmond-вебсвк-2), выполните следующий командлет:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Если CAB-файл находится на компьютере, отличном от того, на котором запущена служба (Service: Redmond-вебсвк-3), выполните следующий командлет:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

5.  На панели навигации слева выберите пункт **Клиенты**, а затем — **обновление устройства**.

6.  На странице **обновление устройства** выберите обновление в списке, а затем выполните одно из указанных ниже действий.
    
      - **Отмена ожидающего обновления.** Чтобы запретить развертывание выбранного обновления на устройствах вашей организации, откройте меню **действия** и выберите пункт **отменить ожидающие обновления**.
    
      - **Утверждение обновления.** Чтобы разрешить развертывание выбранного обновления на устройствах своей организации, откройте меню **действия** и выберите пункт **утвердить**.
    
      - **Восстановите обновление.** Чтобы разрешить развертывание ранее одобренных обновлений на устройствах своей организации, откройте меню **действия** и выберите команду **восстановить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

