---
title: 'Lync Server 2013: Настройка ссылок на сетевой регион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Настройка ссылок на сетевой регион в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Вы можете настроить связи между двумя сетевыми областями в рамках управления допуском звонков (CAC). Регионы в сети связаны по ГЛОБАЛЬным сетевым подключениям. С помощью панели управления Lync Server вы можете определить связь между двумя областями сети и задать ограничения пропускной способности для звуковых и видеоподключений между этими регионами. Подробнее об удалении ссылки на существующий сетевой регион можно узнать [в разделе Удаление ссылок на области сети в Lync Server 2013](lync-server-2013-deleting-network-region-links.md).

<div>

## <a name="to-create-a-network-region-link"></a>Создание ссылки на сетевой регион

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем щелкните **ссылку Region (регион**).

4.  На странице " **ссылка на регион** " нажмите кнопку **создать**.

5.  В поле " **ссылка на новый регион**" введите значение из поля **имя** .
    
    <div>
    

    > [!NOTE]  
    > Это значение должно быть уникальным в рамках развертывания Lync Server 2013.

    
    </div>

6.  В раскрывающемся списке **сетевой регион \#1** выберите один из двух областей, которые нужно связать.

7.  В раскрывающемся списке **сетевой регион \#2** выберите другой регион, который нужно связать. Этот регион должен отличаться от региона, выбранного для сетевого региона \#1.

8.  Необязательно Если вы хотите помещать ограничения на пропускную способность для звуковых и видеозвонков в этих регионах, выберите профиль политики пропускной способности из раскрывающегося списка **политика пропускной способности** .

9.  Нажмите **Исполнить**.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>Изменение ссылки на сетевой регион

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем щелкните **ссылку Region (регион**).

4.  На странице " **ссылка на регион** " щелкните ссылку на область, которую вы хотите изменить.

5.  В меню **Правка** щелкните **Подробнее**.

6.  В **ссылке Изменить регион**можно изменить связанные с ней регионы или профиль политики пропускной способности для этой ссылки.

7.  Нажмите **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление ссылок на сетевой регион в Lync Server 2013](lync-server-2013-deleting-network-region-links.md)  


[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
