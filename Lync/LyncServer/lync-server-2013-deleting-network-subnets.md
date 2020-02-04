---
title: 'Lync Server 2013: удаление подсетей сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Удаление подсетей сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Для удаления подсети вы можете использовать описанную ниже процедуру. С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые подсети. Сведения о создании и изменении подсетей сети можно найти [в разделе Создание или изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

В большинстве развертываний Microsoft Lync Server 2013 там, где реализовано управление допуском звонков (CAC), обычно это большое количество подсетей. По этой причине лучше всего настроить подсети из командной консоли Lync Server Management Shell. Из него вы можете вызвать **New-кснетворксубнет** в сочетании с командлетом Windows PowerShell **Import-CSV**. Используя эти командлеты вместе, вы можете прочитать параметры подсети из CSV-файла и одновременно создать несколько подсетей. Примеры создания подсетей из CSV-файла можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Удаление сетевой подсети

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **подсеть**.

4.  На странице **Subnet (подсеть** ) выберите подсеть, которую вы хотите удалить.
    
    <div>
    

    > [!NOTE]  
    > Вы можете удалить более одной подсети за один раз. Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая нажатой клавишу CTRL. Кроме того, чтобы выбрать все подсети, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .

    
    </div>

5.  В меню **Правка** выберите команду **Удалить**.

6.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

