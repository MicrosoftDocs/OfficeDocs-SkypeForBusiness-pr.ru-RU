---
title: 'Lync Server 2013: Просмотр обновлений программного обеспечения для устройств в Организации'
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
ms.openlocfilehash: ce1940f92860d5ccd2d66c53a0a4da16cebada24
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Просмотр обновлений программного обеспечения для устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

С помощью Lync Server 2013 вы можете просматривать обновления программного обеспечения для устройств организации и управлять ими с помощью веб-службы обновления устройств. Эти обновления доступны в САВ-файлах на веб-сайте службы поддержки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091). После загрузки CAB-файла выполните командлет **Import-CSDeviceUpdate** , чтобы импортировать правила обновления устройств из CAB-файла. Подробные сведения о командлете **Import – CSDeviceUpdate** можно найти в статье [Import – CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) в документации по консоли управления Lync Server.

<div>


> [!TIP]  
> Перед развертыванием нового обновления в организации проверьте, что оно работает правильно на тестовом устройстве.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Просмотр обновлений ПО для устройств объединенных коммуникаций

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  На веб-сайте службы поддержки [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)корпорации Майкрософт по адресу Скачайте CAB-файл в папку на компьютере с Lync Server 2013 (например, C\\:\\Updates UCUpdates. cab).

3.  Импортируйте правила обновления устройств из файла C:\\Updates\\UCUpdates. cab, выполнив один из следующих командлетов:
    
      - Если CAB-файл расположен на том же компьютере, на котором работает обновляемая служба (service:Redmond-websvc-2), запустите следующий командлет:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Если CAB-файл расположен на другом компьютере, на котором не работает обновляемая служба (service:Redmond-websvc-3), запустите следующий командлет:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

5.  В левой панели навигации щелкните элемент **Клиенты**, а затем элемент **Обновление устройств**.

6.  На странице **Обновление устройств** щелкните обновление в списке, а затем выполните одно из следующих действий:
    
      - **Отмена отложенного обновления.** Чтобы запретить развертывание выбранного обновления на устройства организации, откройте меню **Действие** и выберите команду **Отменить отложенные обновления**.
    
      - **Утверждение обновления.** Чтобы разрешить развертывание выбранного обновления на устройства организации, откройте меню **Действие** и выберите команду **Утвердить**.
    
      - **Восстановление обновления.** Чтобы разрешить развертывание на устройства организации ранее утвержденного обновления, откройте меню **Действие** и выберите команду **Восстановить**.

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

