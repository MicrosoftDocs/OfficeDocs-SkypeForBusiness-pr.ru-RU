---
title: 'Lync Server 2013: Устранение неполадок в панели управления Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e670dc0871490e513023d3276ad80126be173b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Устранение неполадок с панелью управления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-07-28_

В этом разделе представлены сведения и процедуры, которые помогут устранить неполадки при доступе к панели управления Lync Server 2013.

<div>

## <a name="internet-browser-requirements"></a>Требования к Интернет-браузеру

Для панели управления Lync Server необходимо установить надстройку браузера Microsoft Silverlight версии 4.0.50524.0 или последней версии. Если Silverlight не установлен или если установлена более ранняя версия, следуйте инструкциям в сообщении, чтобы установить требуемую версию.

<div>


> [!NOTE]  
> Другие требования к программному обеспечению для панели управления Lync Server относятся к операционной системе, в которой можно установить панель управления Lync Server и все остальные средства администрирования Lync Server 2013. Для получения дополнительных сведений обратитесь к разделу <A href="lync-server-2013-server-and-tools-operating-system-support.md">Поддержка серверов и средств операционной системы в Lync Server 2013</A> в документации по поддержке.



</div>

Если ваш Интернет-браузер блокирует установку Silverlight из-за соображений безопасности, добавьте URL-адрес, который открывает панель управления Lync Server, в список надежных сайтов. В параметрах безопасности Internet Explorer убедитесь, что параметр **Запускать элементы ActiveX и подключаемые модули****включен**. Дополнительные сведения см [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060). Кроме того, убедитесь, что браузер настроен для использования SSL 3.0.

Если Интернет-браузер настроен для использования прокси-сервера, то убедитесь, что задан обход прокси-сервера для сайтов, которые автоматически определяются как внутренние сайты. Можно также добавить этот адрес в список исключений браузера в параметрах конфигурации прокси-сервера.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Требования к записи DNS и к сертификату для URL-адреса административного доступа

Если вы настроили простой URL-адрес для доступа к панели управления Lync Server, убедитесь, что вы также настроили статическую запись ресурса узла (DNS) узла (A) и сертификат, необходимый для использования этого URL-адреса административного доступа. Если изменить базовый URL-адрес в любой момент времени, убедитесь, что изменение отражается в соответствующей записи DNS и в сертификате, а также при запуске командлета *Enable-CsComputer* на каждом директоре и сервере переднего плана, чтобы зарегистрировать изменение. Подробные сведения см. в следующих разделах документации по планированию.

  - [Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Требования DNS для простых URL-адресов в Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Пошаговые процедуры настройки URL-адреса административного доступа приведены в статье [изменение или Настройка простых URL-адресов в Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) в документации по развертыванию.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Требования служб IIS

Панель управления Lync Server — это один из компонентов Lync Server 2013, требующих служб IIS. В частности, следует убедиться, что включены функции перенаправления HTTP и проверки подлинности Windows, и что служба веб-публикаций (W3SVC) выполняется.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Зависимость от службы веб-публикаций (службы Windows)

После остановки службы публикации в Интернете невозможно получить доступ к панели управления Lync Server. Необходимо перезапустить эту службу с помощью консоли управления (MMC) служб Windows.

**Запуск службы веб-публикаций**

1.  Войдите на компьютер, на котором установлена служба веб-публикации в составе служб IIS.

2.  Нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **Службы**.

3.  Щелкните правой кнопкой мыши **службу веб-публикаций** и выберите команду **Пуск**.

</div>

<div>

## <a name="application-pool-mode"></a>Режим пула приложений

Настройте службы IIS таким образом, чтобы пул приложений CsManagementAppPool использовал учетную запись сетевой службы в качестве удостоверения своей модели процесса.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Пользовательские права и разрешения

Необходимо войти на панель управления Lync Server с помощью учетной записи домена, которая является членом группы CsAdministrator, или с помощью учетной записи, которой делегированы права и разрешения пользователей. Вы не можете войти на панель управления Lync Server, используя учетную запись локального компьютера. Дополнительные сведения о делегировании административных задач с помощью управления доступом на основе ролей (RBAC) можно найти в статье [Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.

Если вы используете простой URL-адрес для доступа к панели управления Lync Server, убедитесь, что веб-серверы добавлены в группы RTCUniversalServerAdmins и RTCUniversalUserAdmins.

</div>

<div>

## <a name="see-also"></a>См. также


[Lync Server 2013 административные средства](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

