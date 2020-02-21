---
title: 'Lync Server 2013: удаление сетевых подсетей'
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
ms.openlocfilehash: 05e47875007bd9fb7893ad952bea6772d2d9df9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Удаление сетевых подсетей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Для удаления подсети можно использовать следующую процедуру. С помощью панели управления Lync Server можно создавать, изменять и удалять подсеть. Дополнительные сведения о создании или изменении подсетей сети приведены [в статье Создание или изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

В большинстве развертываний Microsoft Lync Server 2013, где реализован контроль допуска звонков (CAC), как правило, существует большое количество подсетей. Поэтому часто лучше настроить подсети из командной консоли Lync Server. Отсюда вы можете вызвать командлет **New-CsNetworkSubnet** в сочетании с командлетом Windows PowerShell **Import-CSV**. Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей. Примеры создания подсетей из CSV-файла см. в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Удаление подсети

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Конфигурация сети** и выберите элемент **Подсеть**.

4.  На странице **подсетей** щелкните подсеть, которую следует удалить.
    
    <div>
    

    > [!NOTE]  
    > Можно одновременно удалять несколько подсетей. Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая клавишу CTRL нажатой. Можно также выбрать все подсети, нажав пункт <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.

    
    </div>

5.  В меню **Правка** выберите команду **Удалить**.

6.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение сетевых подсетей в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

