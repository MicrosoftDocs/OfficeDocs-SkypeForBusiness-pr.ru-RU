---
title: Настройка основного сервера управления
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2019.'
ms.openlocfilehash: a4fda367307b99bb952e6673b3b4d1c2967299c6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824003"
---
# <a name="configure-the-primary-management-server"></a>Настройка основного сервера управления

**Сводка:** Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2019.

Чтобы воспользоваться всеми преимуществами новых возможностей мониторинга работоспособности, включенных в Skype для бизнеса Server 2019, необходимо сначала назначить компьютер для работы в качестве основного сервера управления. Затем необходимо установить System Center Operations Manager 2012 с пакетом обновления 1 (SP1) или R2 либо System Center Operations Manager 2007 R2 на этом компьютере. Кроме того, необходимо сначала установить поддерживаемую версию SQL Server, которая будет выступать в качестве серверной базы данных Operations Manager.

При установке System Center Operations Manager вам потребуется установить все компоненты этого продукта, в том числе следующие:

- рабочую базу данных;

- Сервер

- консоль;

- Командлеты Windows PowerShell

- веб-консоль;

- отчеты;

- хранилище данных.

> [!IMPORTANT]
> Перед установкой System Center Operations Manager 2012 необходимо установить[распространяемый пакет Microsoft Report Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442).

Сведения об этих программах и их установке см. по следующим ссылкам:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Имейте в виду, что вы можете использовать только один корневой сервер управления для развертывания Skype для бизнеса Server.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Импорт пакетов управления для Skype для бизнеса Server 2019

Вы можете расширять возможности System Center Operations Manager, устанавливая пакеты управления (программное обеспечение, которое определяет, какие элементы отслеживает диспетчер операций System Center Operations Manager), как эти элементы должны отслеживаться и как будут запускаться оповещения. отчета. Skype для бизнеса Server 2019 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:

- **Пакет управления компонентом и пользовательским** интерфейсом (Microsoft.ls.2019.Monitoring.ComponentAndUser.MP) отслеживает проблемы в Skype для бизнеса Server, записанные счетчиками производительности, которые регистрируются в журналах событий или регистрируются в записях сведений о вызовах (кдрс) или в базах данных качества взаимодействия (QoE). Для устранения критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов по электронной почте, мгновенным сообщениям или SMS-сообщениям. (SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)

    > [!NOTE]
    >  Дополнительные сведения о настройке уведомлений Operations Manager: [Настройка уведомлений](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Активный пакет управления мониторингом** (Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP) проверит ключевые компоненты сервера Skype для бизнеса, например вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся в телефонной сети общего пользования (PSTN). Такая проверка выполняется с помощью командлетов искусственных транзакций Skype для бизнеса Server. Например, командлет **Test-CsIM** позволяет смоделировать сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями. В случае сбоя при моделировании сеанса формируется оповещение.

Одним из важнейших этапов является импорт пакетов управления. Если они не импортированы, в Skype для бизнеса Server невозможно наблюдать за событиями и выполнять искусственные транзакции с помощью Operations Manager.

Пакет управления компонентом и пользовательским интерфейсом используется для мониторинга только Skype для бизнеса Server 2019. Если у вас есть сценарий сосуществования, в котором установлены как Skype для бизнеса Server 2019, так и Skype для Business Server 2015, вы должны продолжать использовать пакеты управления Skype для бизнеса Server 2015 для компьютеров, использующих Skype для бизнеса Server 2015.

> [!NOTE]
> Пакеты управления для Skype для бизнеса Server 2019 включают компонент Skype для бизнеса Server 2019 и пакет управления пользователями, а также пакет управления для мониторинга Skype для бизнеса Server 2019.

Для импорта пакетов управления можно использовать следующие средства:

- **System Center Operations Manager** С помощью этого метода вы можете добавить мониторинг для Skype для бизнеса Server с помощью Operations Manager.

- **Оболочка Operations Manager** С помощью консоли Operations Manager можно импортировать их напрямую или устранить проблемы, возникающие при импорте пакетов управления, используя консоль System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Импорт пакетов управления с помощью System Center Operations Manager

1. Загрузите файл SkypeForBusiness2019ManagementPacks. msi с веб-сайта Microsoft Downloads и установите MSI.

2. В System Center Operations Manager щелкните элемент **Администрирование**.

3. В области "Администрирование" щелкните правой кнопкой мыши **пакеты управления**и выберите пункт **Импорт пакетов управления**.

4. В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Добавить**, затем щелкните **Добавить с диска**.

5. В диалоговом окне **Подключение к каталогу в Интернете** щелкните **Нет**.

6. В диалоговом окне **Выбор пакетов управления для импорта** найдите и выберите файлы Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp и Microsoft.ls.2019.Monitoring.ComponentAndUser.MP, а затем нажмите кнопку **Открыть**. Для выбора нескольких файлов в этом диалоговом окне щелкните первый файл, затем, удерживая нажатой клавишу Ctrl, щелкните последующие файлы.

7. В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Установить**. Сообщение об ошибке и сбой установки, как правило, указывают на то, что папка, в которой находятся файлы пакетов управления, защищена функцией контроля учетных записей Windows. В этом случае скопируйте файлы в другую папку и запустите процесс импорта и установки заново.

8. В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Закрыть**. Процесс импорта и установки может продолжаться несколько минут.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Импорт пакетов управления с помощью оболочки Operations Manager

Как правило, пакеты управления удобнее импортировать с консоли Operations Manager. Однако при возникновении ошибки и сбое импорта в консоли не всегда отображаются необходимые сведения об ошибке. В оболочке Operations Manager представлена более подробная информация. В случае неполадок при импорте пакета управления средствами Operations Manager импортируйте этот пакет с помощью оболочки Operations Manager. Информация, отображаемая в оболочке Operations Manager, позволяет определить причину сбоя импорта.

1. Нажмите кнопку **Пуск** и щелкните **Все программы**, **Microsoft System Center 2012**, **Operations Manager**, затем **Оболочка Operations Manager**.

2. В командной строке Operations Manager введите указанную ниже команду, используя фактический путь к копии файла Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД.

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. После импорта первого пакета управления повторите процесс, указав путь к копии файла Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
