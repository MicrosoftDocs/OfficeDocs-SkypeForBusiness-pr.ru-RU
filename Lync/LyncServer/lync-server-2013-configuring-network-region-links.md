---
title: 'Lync Server 2013: Настройка связей между сетевыми областями'
description: 'Lync Server 2013: Настройка связей между сетевыми областями.'
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
ms.openlocfilehash: b92593f3b8fcd5fe3307a9c193ed7cddcf6dfce0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547015"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a>Настройка связей между областями сети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC). Регионы в сети связываются с помощью физического подключения глобальной сети. С помощью панели управления Lync Server вы можете определить ссылку между двумя областями сети и установить ограничения пропускной способности для звуковых и видеоподключений между этими областями. Дополнительные сведения об удалении существующей связи между областями сети содержатся [в статье Удаление связей между областями сети в Lync Server 2013](lync-server-2013-deleting-network-region-links.md).

<div>

## <a name="to-create-a-network-region-link"></a>Создание связи сетевой области

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.

4.  На странице **Связь между областями** нажмите кнопку **Создать**.

5.  В окне **Создание связи между областями** введите значение в поле **Имя**.
    
    <div>
    

    > [!NOTE]  
    > Это значение должно быть уникальным в рамках развертывания Lync Server 2013.

    
    </div>

6.  В раскрывающемся списке **область сети \# 1** выберите одну из двух областей, которые необходимо связать.

7.  В раскрывающемся списке **область сети \# 2** выберите другой регион, который необходимо связать. Этот регион должен отличаться от региона, выбранного для области сети \# 1.

8.  (Необязательно) Если нужно наложить ограничения полосы пропускания на аудио- или видеовызовы между этими областями, выберите профиль политики в раскрывающемся списке **Политика полосы пропускания**.

9.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>Изменение связи сетевой области

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.

4.  На странице **Связь между областями** щелкните связь, которую нужно изменить.

5.  В меню **Правка** выберите команду **Показать подробности**.

6.  В окне **Изменение связи между областями** вы можете изменить связанные области или профиль политики пропускной способности для этой связи.

7.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление связей между областями сети в Lync Server 2013](lync-server-2013-deleting-network-region-links.md)  


[New — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
