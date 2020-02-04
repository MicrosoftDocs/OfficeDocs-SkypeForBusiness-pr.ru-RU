---
title: 'Lync Server 2013: обеспечение взаимодействия Lync и Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0125ff4719cd3dfeb65353df747395e596b45dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Обеспечение взаимодействия Lync и Skype в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-12-16_

После того как вы отправили запрос на подготовку, вы можете сосредоточиться на среде Lync Server и административных задачах, необходимых для настройки связи Lync — Skype. В этом разделе предполагается, что администратор сервера Lync Server развернул сервер Lync Server и настроил внешний доступ. Дополнительные сведения о настройке внешнего доступа для Lync Server можно найти [в разделе Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) и [развертывание внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Для подготовки среды Lync Server для Lync — возможности подключения к Skype администратор сервера Lync Server должен выполнить следующие три задачи:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. настройка федерации и PIC;

Для того чтобы пользователи Skype могли общаться с пользователями Lync в вашей организации, требуется Федерация. Общедоступная служба обмена мгновенными сообщениями (PIC) — это класс Федерации, и он должен быть настроен для предоставления пользователям Lync возможности общаться с пользователями Skype. Федерация и PIC настраиваются с помощью панели управления Lync Server, показанной ниже.

![Отображение PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Отображение PIC")

<div>


> [!IMPORTANT]  
> Федерация PIC больше не поддерживается в Live Communication Server 2005 с пакетом обновления 1 (SP1) и Office Communications Server 2007. Поддерживаются следующие платформы для интеграции PIC: Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. настройка не менее одной политики для поддержки доступа федеративных пользователей;

С помощью панели управления Lync Server администратор должен настроить одну или несколько политик доступа внешних пользователей, чтобы указать, могут ли пользователи Skype работать вместе с внутренними пользователями Lync Server.

![Политики](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Политики")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Настройка параметров поставщика в Skype PIC для Lync

С помощью командной консоли Lync Server администратор должен настроить политику клиента Lync, чтобы показать Skype как дополнительный поставщик PIC.

<div>


> [!NOTE]  
> Пользователи поставщиков услуг общедоступной службы обмена мгновенными сообщениями (PIC) не могут принимать участие в СООБЩЕНИЯх, голосовых и видеоконференциях в вашей организации, пока не настроите по крайней мере одну политику (шаг 2, ранее в этой процедуре), чтобы обеспечить поддержку подключения к общедоступным СООБЩЕНИЯм



</div>

1.  Чтобы настроить федерацию и PIC, обратитесь к разделу "Включение и отключение служб федерации и общедоступной службы обмена мгновенными сообщениями" [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).

2.  Для настройки хотя бы одной политики для поддержки федеративного доступа пользователей обратитесь к разделу Настройка политики для управления доступом пользователей (Public [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)Users).

**Изменение существующего поставщика Messenger или Skype PIC и его настройка для Skype**

1.  На сервере переднего плана Lync Server откройте командную консоль Lync Server Management Shell.

2.  Выполните две следующие команды:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Если у вас еще нет провайдера PIC в вашей среде и вы создаете новый поставщик PIC, вам не нужно запускать командлет <STRONG>Remove-кспубликпровидер</STRONG> .

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Добавлена в Lync Server 2013 CU5 &amp; Lync для настольных компьютеров в Office 2013 с пакетом обновления 1 (SP1), Намедекоратионраутингдомаин и намедекоратионексклудеддомаинлист улучшают ситуацию, когда пользователи Lync добавляют контакты Skype, необходимые для того, чтобы "выявлять" домены, не связанные с Microsoft, для идентификации и направления их в Skype (формат: User (contoso. com) @msn. com) Эти новые параметры позволят автоматически выполнять форматирование адреса пользователя, указанного в диалоговом окне "Добавление контактов Skype" с параметром NameDecorationRoutingDomain (для которого должно быть указано значение "msn.com"), если отсутствуют домены из NameDecorationExcludedDomainList (в настоящее время возможна поддержка доменов msn.com, live.com, Hotmail.com, outlook.com).

    
    </div>

3.  В клиенте Lync теперь вы можете выбрать Skype в качестве поставщика PIC и добавить клиент Skype, указав учетную запись Майкрософт. Кроме того, пользователь Skype, выполнивший слияние и выполнившего вход с помощью учетной записи Майкрософт, может отправлять запросы на контакт пользователям Lync. Дополнительные сведения об учетных записях Майкрософт можно найти [в статье что такое учетная запись Майкрософт?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Дополнительные сведения о добавлении клиентов в Lync можно найти [в разделе Использование связи Lync — Skype для Lync Server 2013 в качестве конечных пользователей](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Добавить абонента Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Добавить абонента Skype")

4.  Подробные сведения об изменении размещенных поставщиков можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)разделе Создание или изменение размещенных служб федерации SIP.

Это все административные задачи, которые нужно выполнить на сервере. Теперь вы готовы к установке Lync – подключение к Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

