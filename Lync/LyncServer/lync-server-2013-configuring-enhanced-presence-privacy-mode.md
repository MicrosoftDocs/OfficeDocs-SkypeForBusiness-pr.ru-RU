---
title: 'Lync Server 2013: Настройка режима конфиденциальности для расширенного присутствия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Настройка режима конфиденциальности для расширенного присутствия в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-12-08_

С улучшенным режимом конфиденциальности сведений о присутствии пользователи могут ограничивать сведения о присутствии, чтобы они были видны только контактам, указанным в их списке контактов в Lync 2013. В командлетах **New-кспривациконфигуратион** и **Set-кспривациконфигуратион** этот параметр управляется параметром енаблепривацимоде. Если для Енаблепривацимоде установлено значение true, параметр ограничения сведений о присутствии для контактов становится доступен в параметрах состояния Lync 2013. Если для Енаблепривацимоде задано значение false, пользователи могут выбрать, как всегда разрешать всем пользователям просматривать сведения о присутствии или придерживаться всех последующих изменений, внесенных администратором в режим конфиденциальности.

<div>


> [!IMPORTANT]  
> Параметры конфиденциальности для Lync 2013 и Lync 2010 не соблюдаются в предыдущих версиях (Microsoft Office Communicator 2007 R2 или Microsoft Office Communicator 2007). Если для предыдущих версий Office Communicator разрешен вход, состояние пользователя Lync 2013, контактные данные или изображение могут просматривать пользователи, у которых нет разрешения на его просмотр. Кроме того, параметры конфиденциальности пользователя Lync 2013 сбрасываются, если в дальнейшем он входит в предыдущую версию Communicator.<BR>По этим причинам перед включением режима конфиденциальности для расширенного присутствия в сценарии миграции выполните указанные ниже действия. 
> <UL>
> <LI>
> <P>Убедитесь, что у каждого пользователя установлено приложение Lync 2013.</P>
> <LI>
> <P>Определите правило политики для клиентской версии, чтобы не допустить вход из предыдущих версий Communicator.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Включение расширенного режима конфиденциальности присутствия

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Выполните следующую команду.
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Эта команда включает режим конфиденциальности для всех параметров конфигурации конфиденциальности, которые в настоящее время используются в Организации. Дополнительные сведения о том, как с помощью расширенных конфигураций политики режима конфиденциальности в Lync Server можно управлять присутствием контакта в клиенте Lync 2013, ознакомьтесь со статьей Microsoft KB [Включение режима конфиденциальности Lync Server расширенные возможности состояние некоторых контактов Lync на "недоступно"](http://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

