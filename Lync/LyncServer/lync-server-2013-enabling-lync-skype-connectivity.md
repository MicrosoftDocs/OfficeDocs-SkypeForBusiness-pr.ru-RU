---
title: 'Lync Server 2013: включение Lync — подключение к Skype'
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
ms.openlocfilehash: 4bb14153739c5f29e88044eae89a1322b046a0a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Включение подключения Lync — Skype в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-12-16_

После отправки запроса на подготовку можно сосредоточиться на среде Lync Server и задачах администрирования, необходимых для настройки подключения Lync — Skype. В этом разделе предполагается, что администратор Lync Server развернул Lync Server и настроил внешний доступ. Дополнительные сведения о настройке внешнего доступа для Lync Server приведены в статье [Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) и [развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Чтобы подготовить среду Lync Server к подключению Lync — Skype, администратор Lync Server должен выполнить следующие три задачи:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Настройка Федерации и PIC

Для предоставления пользователям Skype возможности общаться с пользователями Lync в Организации требуется Федерация. Общедоступная служба обмена мгновенными сообщениями (PIC) — это класс Федерации, который необходимо настроить, чтобы разрешить пользователям Lync общаться с пользователями Skype. Федерация и PIC настраиваются с помощью панели управления Lync Server, показанной ниже.

![Показ PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Показ PIC")

<div>


> [!IMPORTANT]  
> Федерация PIC больше не поддерживается сервером Live Communications 2005 с пакетом обновления 1 (SP1) или Office Communications Server 2007. Поддерживаемыми платформами для Федерации PIC являются Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Настройка по крайней мере одной политики для поддержки федеративного доступа пользователей

С помощью панели управления Lync Server администратор должен настроить одну или несколько политик доступа внешних пользователей, чтобы определить, могут ли пользователи Skype совместно работать с внутренними пользователями Lync Server.

![Политики](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Политики")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Настройка параметров поставщика Skype PIC для Lync

С помощью командной консоли Lync Server администратор должен настроить политику клиента Lync для отображения Skype в качестве дополнительного поставщика PIC.

<div>


> [!NOTE]  
> Пользователи поставщиков услуг общедоступных мгновенных сообщений не могут участвовать в обмене мгновенными сообщениями или аудио-и видеоконференциях в Организации до тех пор, пока не будет настроена хотя бы одна политика (шаг 2, ранее в этой процедуре) для поддержки подключения к общедоступным системам обмена мгновенными сообщениями



</div>

1.  Чтобы настроить федерацию и PIC, обратитесь к разделу "Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).

2.  Чтобы настроить по крайней мере одну политику для поддержки федеративного доступа пользователей, обратитесь к разделу "Настройка политик для управления [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064)общими пользователями".

**Изменение существующего поставщика услуг обмена сообщениями или Skype PIC и настройка его для Skype**

1.  На сервере переднего плана Lync Server откройте командную консоль Lync Server.

2.  Выполните две следующие команды:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Если у вас еще нет поставщика PIC в среде и создается новый поставщик PIC, выполнять командлет <STRONG>Remove – CsPublicProvider</STRONG> не требуется.

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Добавлено в Lync Server 2013 CU5 &amp; для настольных ПК Lync в Office 2013 SP1, Намедекоратионраутингдомаин и намедекоратионексклудеддомаинлист совершенствуют ситуацию, в которой пользователи Lync добавляют контакты Skype, необходимые для "украшения" доменов, отличных от Майкрософт, для идентификации и направления их в Skype (формат: User (contoso. com) @msn. com). Эти новые параметры позволят автоматически форматировать введенные пользователем адреса в диалоговом окне "Добавление контакта Skype" с параметром Намедекоратионраутингдомаин (который должен иметь значение msn.com), если он не содержит домены в Намедекоратионексклудеддомаинлист ( в настоящее время мы можем поддерживать msn.com, live.com, Hotmail.com, outlook.com).

    
    </div>

3.  В клиенте Lync теперь можно выбрать Skype в качестве поставщика PIC и добавить клиент Skype, указав учетную запись Майкрософт. Кроме того, пользователи Skype, которые выполнили слияние и выполнили вход с помощью учетной записи Майкрософт, могут отправлять запрос контакта пользователям Lync. Дополнительные сведения об учетных записях Майкрософт [можно узнать в разделе что такое учетная запись Майкрософт?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Дополнительную информацию о добавлении клиентов в Lync можно узнать [в статье использование подключения Lync — Skype в Lync Server 2013 в качестве конечного пользователя](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Добавление контакта Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Добавление контакта Skype")

4.  Подробную информацию об изменении размещенных поставщиков можно найти в разделе "Создание или изменение размещенных федеративных [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)поставщиков SIP" по адресу.

Это завершает задачи администрирования, которые необходимо выполнить на сервере. Теперь вы можете настроить подключение Lync к Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

