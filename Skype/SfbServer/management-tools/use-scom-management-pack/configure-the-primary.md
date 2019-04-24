---
title: Настройка основного сервера управления
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Сводка: Настройка вашей основной сервер управления сервера, установки System Center Operations Manager и импорт пакетов управления для Скайп для Business Server 2015.'
ms.openlocfilehash: 06dbf8161e2b241bb527c0ca02c9e8210055d409
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197943"
---
# <a name="configure-the-primary-management-server"></a>Настройка основного сервера управления

**Сводка:** Настройте сервер управления, установки System Center Operations Manager и импорт пакетов управления для Скайп для Business Server 2015.

Чтобы пользоваться всеми преимуществами новых возможностей, включенных в Скайп Business Server 2015 мониторинга работоспособности, необходимо сначала назначить компьютер в качестве вашей основной сервер управления сервера. Затем необходимо установить System Center Operations Manager 2012 с пакетом обновления 1 или R2 или System Center Operations Manager 2007 R2 на этом компьютере. Кроме того необходимо сначала установить поддерживаемая версия SQL Server в качестве серверной базы данных Operations Manager.

При установке System Center Operations Manager, необходимо установить все компоненты этого продукта, включая:

- рабочую базу данных;

- Сервер

- консоль;

- Командлеты Windows PowerShell

- веб-консоль;

- отчеты;

- хранилище данных.

> [!IMPORTANT]
> «[Распространяемого пакета Microsoft Report Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442)» должны быть установлены до начала установки System Center Operations Manager 2012.

Сведения об этих программах и их установке см. по следующим ссылкам:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Имейте в виду, что может иметь только один корневой сервер управления каждого Скайп для развертывания Business Server.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Импорт пакетов управления Skype для бизнеса Server 2015

При установке пакетов управления можно расширить возможности System Center Operations Manager — программное обеспечение, которое может отслеживать определяет элементы, System Center Operations Manager, как эти элементы должны отслеживаться и запуска оповещения и отчеты. Скайп для Business Server 2015 включает в себя два пакета управления System Center Operations Manager, которые обеспечивают следующие возможности:

- **Компонент и пакет управления пользователя** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) отслеживает Скайп проблем Business Server записываются в журналы событий, зарегистрированные счетчики производительности или в записи регистрации вызовов (CDR) или базы данных качества взаимодействия (QoE). Для критических проблем System Center Operations Manager можно настроить для сразу же уведомления администраторов с помощью электронной почты, мгновенное сообщение или SMS системы обмена сообщениями. (SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)

    > [!NOTE]
    >  Для получения дополнительных сведений о настройке уведомлений Operations Manager видеть [Настройка уведомлений](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Пакет управления Active мониторинга** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) проактивное тесты ключевые Скайп для бизнеса серверные компоненты, такие как вход в систему, обмен мгновенными сообщениями или выполнение вызовов номер телефона, расположенные на телефонной сети общего пользования (PSTN ). Такая проверка выполняется с помощью командлетов искусственных транзакций Skype для бизнеса Server. Например, командлет **Test-CsIM** позволяет смоделировать сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями. В случае сбоя при моделировании сеанса формируется оповещение.

Одним из важнейших этапов является импорт пакетов управления. Если они не импортированы, в Skype для бизнеса Server невозможно наблюдать за событиями и выполнять искусственные транзакции с помощью Operations Manager.

Пакет управления компонентами и пользователями предназначен только для наблюдения в Skype для бизнеса Server 2015. Если одновременно установлены программы Skype для бизнеса Server 2015 и Lync Server 2013, следует по-прежнему пользоваться пакетами управления Lync Server 2013 для компьютеров Lync Server 2013.

> [!NOTE]
> К пакетам управления для Skype для бизнеса Server 2015 относятся пакет управления компонентами и пользователями Skype для бизнеса Server 2015 и пакет управления активным наблюдением Skype для бизнеса Server 2015.

Для импорта пакетов управления можно использовать следующие средства:

- **System Center Operations Manager** С помощью этого метода используйте Operations Manager для мониторинга для Скайп Business Server.

- **Оболочка Operations Manager** Оболочка Operations Manager можно использовать для прямого импорта или устранения неполадок проблем, возникающих при импорте пакетов управления с помощью консоли System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Импорт пакетов управления с помощью System Center Operations Manager

1. Загрузите файл SkypeForBusiness2015ManagementPacks.msi с веб-страницы загрузки Майкрософт и установите файл msi.

2. В System Center Operations Manager щелкните **Администрирование**.

3. На панели администрирования щелкните правой кнопкой мыши **Пакеты управления**и нажмите кнопку **Импорт пакетов управления**.

4. В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Добавить**, затем щелкните **Добавить с диска**.

5. В диалоговом окне **Подключение к каталогу в Интернете** щелкните **Нет**.

6. В диалоговом окне **Выберите пакеты управления для импорта** найдите и выберите файлы Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, затем нажмите кнопку **Открыть**. Для выбора нескольких файлов в этом диалоговом окне щелкните первый файл, затем, удерживая нажатой клавишу Ctrl, щелкните последующие файлы.

7. В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Установить**. Сообщение об ошибке и сбой установки, как правило, указывают на то, что папка, в которой находятся файлы пакетов управления, защищена функцией контроля учетных записей Windows. В этом случае скопируйте файлы в другую папку и запустите процесс импорта и установки заново.

8. В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Закрыть**. Процесс импорта и установки может продолжаться несколько минут.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Импорт пакетов управления с помощью оболочки Operations Manager

Как правило, пакеты управления удобнее импортировать с консоли Operations Manager. Однако при возникновении ошибки и сбое импорта в консоли не всегда отображаются необходимые сведения об ошибке. В оболочке Operations Manager представлена более подробная информация. В случае неполадок при импорте пакета управления средствами Operations Manager импортируйте этот пакет с помощью оболочки Operations Manager. Информация, отображаемая в оболочке Operations Manager, позволяет определить причину сбоя импорта.

1. Нажмите кнопку **Пуск** и щелкните **Все программы**, **Microsoft System Center 2012**, **Operations Manager**, затем **Оболочка Operations Manager**.

2. В командной строке оболочке Operations Manager введите следующую команду, вставив реальный путь к копии файла Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, затем нажмите клавишу Enter:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. После импорта первого пакета управления повторите процесс, указав путь к копии файла Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
