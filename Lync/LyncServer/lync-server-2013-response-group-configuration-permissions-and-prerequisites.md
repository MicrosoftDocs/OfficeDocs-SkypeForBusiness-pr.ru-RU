---
title: 'Lync Server 2013: разрешения и необходимые условия для настройки группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-05_

Группа ответа — это функция управления голосовым звонком в корпоративной среде. В этой статье описаны действия, которые необходимо выполнить, прежде чем можно будет настроить группу ответа и учетные данные администратора и разрешения, необходимые для выполнения задач настройки.

В этом разделе предполагается, что вы прочитали документацию по планированию, связанную с группой ответа. Подробнее смотрите в разделе [Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) в документации по планированию.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Средства настройки и административные роли

Для настройки группы ответа можно использовать следующие средства администрирования:

  - Панель управления Lync Server

  - настройки группы ответа

  - Командная консоль Lync Server

Для того чтобы настроить группы ответа, необходимо быть членом по крайней мере одной из следующих административных ролей:


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Группа безопасности Active Directory (1)</strong></p></td>
<td><p>Создайте рабочий процесс</p></td>
<td><p>Назначьте менеджера</p></td>
<td><p>Создайте, назначьте агентов, очереди</p></td>
<td><p>Создайте дни праздников и рабочие часы</p></td>
<td><p>Активируйте или деактивируйте рабочий процесс</p></td>
<td><p>Настройте рабочий процесс (Интерактивное речевое взаимодействие (IVR) или сервисную группу)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√(2)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> объект пользователя доменных служб Active Directory должен быть членом указанной группы безопасности Active Directory. Администратор или другой делегированный участник группы Active Directory с необходимыми разрешениями для добавления пользователей в группу безопасности (например, администратор, операторы учета) должен добавить объект пользователя в группу безопасности или группу, чтобы предоставить пользователю возможность выполните указанные функции. <STRONG>(2)</STRONG> только для рабочих процессов, которым ксреспонсеграупадминистратор назначены для ксреспонсеграупманажер. <STRONG>(3)</STRONG> руководитель группы ответа может назначить другой участник ксреспонсеграупманажер рабочему процессу, который уже управляется текущим руководителем. <STRONG>(4)</STRONG> ксвиевонлядминистратор может выполнить только командлет "Get" команд командной консоли для управления Lync Server.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Необходимые условия для настройки группы ответа

Для группы ответа требуются следующие компоненты:

  - приложения

  - "Группа ответа"

  - Языковые пакеты

  - Хранилище файлов (для хранения аудиофайлов)

  - Веб-службы (в том числе средство настройки группы ответа и консоль "вход и выход" агентов)

Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.

Перед настройкой группы ответа может потребоваться выполнить следующие задачи:

  - Включите пользователей для Lync Server 2013 и корпоративной голосовой связи.

  - Изменить файл конфигурации для соответствия стандартам Federal Information Processing (FIPS).

  - Изменить параметры сортировки базы данных для поддержки символов транскрипций ий, мэн, цзан для названий очередей и групп агентов.

<div>

## <a name="enabling-users"></a>Включение пользователей

Первый шаг в настройке группы ответа — создание групп агента. Прежде чем можно будет создать группу агента, необходимо включить пользователей, которые будут агентами группы ответа для Lync Server 2013 и корпоративной голосовой связи. Включение пользователей для Lync Server 2013 обычно является шагом на сервере Enterprise Edition или стандартном развертывании сервера Standard Edition. Дополнительные сведения о включении пользователей для Lync Server 2013 можно найти в разделе [Отключение и повторное включение учетной записи пользователя в Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Включение пользователей для корпоративной голосовой связи обычно является шагом в развертывании Enterprise Voice. Дополнительные сведения можно найти [в разделе Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Соответствие требованиям стандарта FIPS

Данный подраздел касается вас, только если вашей организации необходимо соответствовать федеральному стандарту по (FIPS, США).

To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services. You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data. Для приложения группы ответа это требование распространяется на средство настройки группы ответа и на консоль входа и выхода агента. Дополнительные сведения об этих требованиях можно найти в статье 911722 базы знаний Майкрософт "сообщение об ошибке при доступе к веб-страницам ASP.NET с включенным состоянием отображения после перехода с ASP.NET 1,1 на ASP.NET 2,0" [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)по адресу.

Чтобы изменить файл Web.config, сделайте следующее:

1.  В текстовом редакторе, например в Блокноте, файл Web.config уровня приложения.

2.  Найдите `<system.web>` раздел в файле Web. config.

3.  Добавьте в `<system.web>` раздел `<machineKey>` следующий раздел:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Сохраните файл Web.config.

5.  Перезапустите службу служб IIS, выполнив следующую команду в командной строке:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Поддержка символов транскрипций ий, мэн и цзан

Данный раздел относится к вам, только если вашей организации нужна поддержка подобных символов

<div>


> [!NOTE]  
> Сведения о том, что собой представляют собой символы Yi, Менг и Занг, а также причины, по которым они могут быть важны для вашего развертывания, можно найти <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>в разделе кодировка GB18030.



</div>

Для поддержки символов ий, мэн и цзан необходимо изменить параметры сортировки базы данных Rgsconfig. Измените параметры сортировки столбца **Имя** в следующих таблицах каждой базы данных Rgsconfig:

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Для SQL Server 2008 R2 и SQL Server 2012 используйте параметры сортировки по\_латинский\_General 100 (с учетом диакритических знаков). Если применяются эти параметры сортировки во всех именах объектов не учитывается регистр.

Изменить параметры сортировки можно с помощью Microsoft SQL Server Management Studio. Подробнее об использовании этого средства можно найти в [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)разделе "использование SQL Server Management Studio". Для изменения параметров сортировки выполните следующие действия.

1.  Убедитесь в том, что в Microsoft SQL Server Management Studio разрешено повторное создание таблиц, требующих изменения. Подробные сведения можно найти в разделе "сохранить (неразрешенные)" [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)в диалоговом окне "о себе". Дополнительные сведения о настройке параметров сортировки столбцов можно найти в [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)разделе Инструкции: Настройка параметров сортировки столбцов (визуальные инструменты для баз данных).

2.  Используя Microsoft SQL Server Management Studio подключитесь к базе данных Rgsconfig.

3.  Найдите в базе данных Rgsconfig таблицу, которую требуется изменить, щелкните ее правой кнопкой мыши и выберите **Конструктор**.

4.  Измените параметры сортировки столбца **Имя** и сохраните таблицу.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

