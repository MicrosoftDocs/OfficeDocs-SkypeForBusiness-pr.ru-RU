---
title: 'Lync Server 2013: Включение или отключение обнаружения партнеров Федерации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff9fb4e0b243cc1ce9b51deac1c4021f9b3dff56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526826"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Включение и отключение обнаружения партнеров Федерации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.

<div>


> [!NOTE]  
> В следующей процедуре предполагается, что федерация уже включена для организации. Подробнее о включении Федерации можно узнать в статье <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по операциям.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Включение или отключение автоматического обнаружения федеративных доменов для организации

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.

4.  На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.

5.  В разделе **Изменить настройку пограничного доступа** в области **Разрешить взаимодействие с федеративными пользователями** установите или снимите флажок **Разрешить обнаружение домена партнера**, чтобы включить или отключить автоматическое обнаружение доменов партнеров.

6.  Нажмите кнопку **Сохранить**.

Чтобы разрешить федеративным пользователям совместно работать с пользователями в развертывании Lync Server, вам также необходимо настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей. Дополнительные сведения: [Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) в документации по развертыванию или документации по операциям. Сведения об управлении доступом для определенных федеративных доменов приведены в статье [Manage федеративные домены SIP для Организации в Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Управление ФЕДЕРАТИВНЫМИ поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) и [Управление федеративными партнерами XMPP в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) в документации по операциям.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Включение или отключение обнаружения партнеров Федерации с помощью командлетов Windows PowerShell

Можно управлять обнаружением партнеров Федерации с помощью Windows PowerShell и командлета Set-CsAccessEdgeConfiguration. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>Включение обнаружения партнеров Федерации

  - Чтобы включить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение True ($True). Обратите внимание, что для изменения значения этого свойства необходимо включить маршрутизацию DNS SRV.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>Отключение обнаружения партнеров Федерации

  - Чтобы отключить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

