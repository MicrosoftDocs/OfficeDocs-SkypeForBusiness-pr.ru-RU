---
title: 'Lync Server 2013: разрешения и необходимые условия для настройки группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8787327b386157211e4d83317520358edfec7b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-05_

Группа ответа это функция управления голосовым вызовом корпоративной голосовой связи. В этом разделе описываются действия, которые необходимо выполнить, прежде чем можно будет настроить группу ответа и административные учетные данные и разрешения, необходимые для выполнения задач по настройке.

В этом разделе предполагается, что вы прочитали документацию по планированию, относящуюся к группе ответа. Дополнительные сведения приведены в статье [Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) в документации по планированию.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Инструменты настройки и административные роли

Для настройки группы ответа можно использовать следующие средства администрирования:

  - Панель управления сервера Lync

  - Средство настройки группы ответа

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
<td><p><strong>ксреспонсеграупадминистратор</strong></p></td>
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
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
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
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> объект пользователя доменных служб Active Directory должен быть членом указанной группы безопасности Active Directory в списке. Администратор или другой делегированный участник группы Active Directory с соответствующими разрешениями для добавления пользователей в группу безопасности (например, администратору, операторам учетных записей) должен добавить объект пользователя в указанную группу или группу безопасности, чтобы пользователь мог выполните указанные функции. <STRONG>(2)</STRONG> только для рабочих процессов, назначенных Ксреспонсеграупадминистратор для CsResponseGroupManager. <STRONG>(3)</STRONG> диспетчер группы ответа может назначить другой участник CsResponseGroupManager рабочему процессу, который уже управляется текущим руководителем. <STRONG>(4)</STRONG> CsViewOnlyAdministrator могут выполнять только командлеты "Get" Командная консоль управления Lync Server.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Необходимые условия для настройки группы ответа

Для группы ответа требуются следующие компоненты:

  - служба приложения;

  - приложение группы ответа;

  - Языковые пакеты

  - Хранилище файлов (для хранения аудиофайлов)

  - Веб-службы (включает средство настройки группы ответа и консоль "вход и выход" агентов).

Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.

Перед настройкой группы ответа может потребоваться выполнить следующие задачи:

  - Включение пользователей для Lync Server 2013 и корпоративной голосовой связи.

  - Изменить файл конфигурации для соответствия стандартам Federal Information Processing (FIPS).

  - Изменить параметры сортировки базы данных для поддержки символов транскрипций ий, мэн, цзан для названий очередей и групп агентов.

<div>

## <a name="enabling-users"></a>Включение пользователей

Первым этапом настройки группы ответа является создание групп агентов. Прежде чем можно будет создать группу агентов, необходимо включить пользователей, которые будут агентами для группы ответа для Lync Server 2013 и корпоративной голосовой связи. Включение пользователей для Lync Server 2013 обычно является шагом в развертывании сервера Enterprise Edition или сервера Standard Edition. Дополнительные сведения о включении пользователей для Lync Server 2013 приведены в статье [Отключение или повторное включение учетной записи пользователя для Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Включение пользователей для корпоративной голосовой связи обычно является шагом в развертывании корпоративной голосовой связи. Дополнительную информацию можно узнать [в статье Включение поддержки корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Соответствие требованиям стандарта FIPS

Данный подраздел касается вас, только если вашей организации необходимо соответствовать федеральному стандарту по (FIPS, США).

Чтобы соответствовать стандарту, после установки Web Services необходимо изменить файл Web.config уровня приложения на использование другого криптографического алгоритма. Нужно указать, чтобы ASP.NET использовал алгоритм Triple Data Encryption Standard (3DES) для обработки данных о состоянии просмотра. Для приложения группы ответа это требование применяется к средству настройки группы ответа, а также к консоли входа и выхода агента. Сведения об этих требованиях можно найти в статье 911722 базы знаний Майкрософт "сообщение об ошибке при доступе к веб-страницам ASP.NET с включенным состоянием отображения после обновления ASP.NET 1,1 до ASP.NET 2,0" по адресу [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183)".

Чтобы изменить файл Web.config, сделайте следующее:

1.  В текстовом редакторе, например в Блокноте, файл Web.config уровня приложения.

2.  В файле Web. config выберите `<system.web>` раздел.

3.  Добавьте в `<system.web>` раздел `<machineKey>` следующий раздел:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Сохраните файл Web.config.

5.  Перезапустите службу служб IIS, выполнив следующую команду в командной строки:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Поддержка символов транскрипций ий, мэн и цзан

Данный раздел относится к вам, только если вашей организации нужна поддержка подобных символов

<div>


> [!NOTE]  
> Сведения о том, что представляют собой символы Yi, Мэн и подобных, а также причины, по которым они могут быть важны для развертывания, можно узнать в статье <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>кодировки GB18030.



</div>

Для поддержки данных символов необходимо изменить параметры сортировки базы данных Rgsconfig. Измените параметры сортировки столбца **Название** в следующих таблицах каждой базы данных Rgsconfig:

  - dbo. ажентграупс

  - dbo. BusinessHours

  - dbo. холидайсетс

  - dbo. Очереди

  - dbo. Выгружен

Для SQL Server 2008 R2 и SQL Server 2012 используйте параметры сортировки латиницы\_General\_100 (с учетом диакритических знаков). При использовании этих параметров сортировки все имена объектов не учитывают регистр.

Изменить параметры сортировки можно с помощью Microsoft SQL Server Management Studio. Дополнительные сведения об использовании этого средства приведены в [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184)разделе "использование SQL Server Management Studio". Чтобы изменить параметры сортировки, выполните следующее:

1.  Убедитесь в том, что SQL Server Management Studio настроен так, что можно было бы вносить изменения, требующие пересоздания таблиц. Дополнительные сведения см. в разделе "сохранение (не разрешено)" [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186)в диалоговом окне "сохранение (запрещен)". Дополнительные сведения о настройке параметров сортировки столбцов приведены в разделе "инструкции: Set collation Columns (визуальные инструменты для баз данных) [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185)" в.

2.  Используя Microsoft SQL Server Management Studio подключитесь к базе данных Rgsconfig.

3.  Найдите нужную таблицу в базе данных Rgsconfig, щелкните ее правой кнопкой мыши и выберите **Конструктор**.

4.  Измените параметры сортировки столбца **Название** и сохраните таблицу.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

