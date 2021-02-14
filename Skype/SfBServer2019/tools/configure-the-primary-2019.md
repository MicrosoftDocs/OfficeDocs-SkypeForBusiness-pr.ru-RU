---
title: Настройка основного сервера управления
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2019.
ms.openlocfilehash: 872459f99f2e620d3d34db1196a8618476650c98
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806069"
---
# <a name="configure-the-primary-management-server"></a>Настройка основного сервера управления

**Сводка:** Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2019.

Чтобы в полной мере воспользоваться новыми возможностями мониторинга состояния, включенными в Skype для бизнеса Server 2019, необходимо сначала назначить компьютер для работы в качестве основного сервера управления. Затем на этом компьютере необходимо установить System Center Operations Manager 2012 с sp1 или R2 или System Center Operations Manager 2007 R2. Кроме того, сначала необходимо установить поддерживаемую версию SQL Server, чтобы она функционировала в качестве базы данных тыловой базы данных Operations Manager.

При установке System Center Operations Manager необходимо установить все компоненты этого продукта, в том числе:

- рабочую базу данных;

- Server

- Консоль

- Командлеты Windows PowerShell

- веб-консоль;

- Отчётность

- хранилище данных.

> [!IMPORTANT]
> Перед установкой System Center Operations Manager 2012 необходимо установить распространяемый пакет "Microsoft[Report Viewer 2010".](https://www.microsoft.com/download/details.aspx?id=6442)

Подробные сведения об этих продуктах и их установке см. по следующим ссылкам:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Помните, что для каждого развертывания Skype для бизнеса Server может быть только один корневой сервер управления.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Импорт пакетов управления Skype для бизнеса Server 2019

Вы можете расширить возможности System Center Operations Manager, установив пакеты управления — программное обеспечение, которое определяет, какие элементы System Center Operations Manager может отслеживать, как следует отслеживать эти элементы, а также как следует запускать оповещения и сообщать о них. Skype для бизнеса Server 2019 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:

-  Пакет управления компонентами и пользователями (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) отслеживает проблемы Skype для бизнеса Server, зарегистрированные в журналах событий, зарегистрированные счетчиками производительности или зарегистрированные в базах данных регистрации вызовов (CDRs) или качества обслуживания (QoE). Для критических проблем System Center Operations Manager можно настроить для немедленного уведомления администраторов с помощью электронной почты, мгновенных сообщений или SMS-сообщений. (SMS или служба коротких сообщений — это технология, используемая для отправки текстовых сообщений с одного мобильного устройства на другое.)

    > [!NOTE]
    >  Подробные сведения о настройке уведомления Operations Manager см. в [подстройки "Настройка уведомлений".](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)

- Пакет **управления active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) заблаговременно тестирует ключевые компоненты Skype для бизнеса Server, такие как вход в систему, обмен мгновенными сообщениями или звонки на телефон, расположенный в телефонной сети общего пользования (STN). Эти тесты проводятся с помощью синтетического транзакции Skype для бизнеса Server. Например, командлет **Test-CsIM** имитирует сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями. Если эта имитированная беседа не удалась, создается оповещение.

Импорт пакетов управления является критически важным этапом. Если пакеты управления не импортировать, вы не сможете использовать Operations Manager для отслеживания событий Skype для бизнеса Server или запуска искусственных транзакций Skype для бизнеса Server.

Пакет управления компонентами и пользователями используется для отслеживания только Skype для бизнеса Server 2019. Если вы находитесь в сценарии сосуществования, в котором установлены Skype для бизнеса Server 2019 и Skype для бизнеса Server 2015, следует продолжать использовать пакеты управления Skype для бизнеса Server 2015 для компьютеров Skype для бизнеса Server 2015.

> [!NOTE]
> Пакеты управления для Skype для бизнеса Server 2019 включают пакеты управления компонентами и пользователями Skype для бизнеса Server 2019 и Skype для бизнеса Server 2019 Active Monitoring Management Pack.

Для импорта пакетов управления можно использовать следующие средства:

- **System Center Operations Manager** С помощью этого метода operations Manager добавляет мониторинг для Skype для бизнеса Server.

- **Operations Manager Shell** Консоль Operations Manager можно использовать для прямого импорта или устранения проблем, которые могут возникнуть при импорте пакетов управления с помощью консоли System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Импорт пакетов управления с помощью System Center Operations Manager

1. Скачайте SkypeForBusiness2019ManagementPacks.msi из веб-загрузки Microsoft и установите MSI.

2. В System Center Operations Manager щелкните **"Администрирование".**

3. На панели Администрирование щелкните правой кнопкой **Пакеты управления** и выберите команду **Импорт пакетов управления**.

4. В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Добавить** и щелкните элемент **Add from disk** (Добавить с диска).

5. В **диалоговом окне "Подключение** к интернет-каталогу" нажмите кнопку **"Нет"**

6. В **диалоговом** окне "Выбор пакетов управления для импорта" найдите и выберите файлы, Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2019.Monitoring.ComponentAndUser.mp нажмите кнопку **"Открыть".** Чтобы выбрать несколько файлов в диалоговом окне, щелкните первый файл, а затем удерживайте клавишу CTRL и щелкните последующие файлы.

7. В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Установить**. Если отображается сообщение об ошибке и установка завершается со сбоем, обычно это указывает на то, что файлы пакетов управления находятся в папке, защищенной функцией контроля учетных записей Windows. В этом случае скопируйте файлы в другую папку, а затем перезапустите процесс импорта и установки.

8. В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Закрыть**. Для завершения процесса импорта и установки может потребоваться несколько минут.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Импорт пакетов управления с помощью оболочки Operations Manager

В общем, проще импортировать пакеты управления с помощью консоли Operations Manager. Однако при ошибке и с ошибке импорта консоль не всегда предоставляет соответствующие отчеты об ошибках. Для сравнения, в оболочке Operations Manager предоставляется подробная информация. Если вы используете Operations Manager и при импорте пакета управления столкнулись с проблемой, импортировать пакет с помощью оболочки Operations Manager. Сведения, предоставляемые в оболочке Operations Manager, помогут определить причину сбой импорта.

1. Нажмите **кнопку**"Начните", выберите "Все **программы", Microsoft System Center 2012**, **"Operations Manager"** и **"Оболочка Operations Manager".** 

2. В Командная команда Operations Manager введите следующую команду, используя фактический путь к копии файла Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp и нажмите ввод:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. После импорта первого пакета управления повторите этот процесс, используя путь к копии файла Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
