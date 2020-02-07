---
title: Подключение приложения для пациентов к Azure API для FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Сведения о том, как подключить приложение пациентов в Microsoft Teams к Azure API для ФХИР (ресурсы для быстрого обеспечения для сферы здравоохранения).
ms.openlocfilehash: 92c5b033215b0e5520b0321042d52579dfb019bf
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827727"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="f59b1-103">Подключение приложения для пациентов к Azure API для FHIR</span><span class="sxs-lookup"><span data-stu-id="f59b1-103">Connect the Patients app to Azure API for FHIR</span></span>

<span data-ttu-id="f59b1-104">Выполните эти действия, чтобы разрешить приложению пациентов в Microsoft Teams получить доступ к интерфейсу API Azure для экземпляра ФХИР.</span><span class="sxs-lookup"><span data-stu-id="f59b1-104">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="f59b1-105">В этой статье предполагается, что у вас есть [API Azure для настройки экземпляра фхир](https://azure.microsoft.com/services/azure-api-for-fhir/) и его настройки в клиенте.</span><span class="sxs-lookup"><span data-stu-id="f59b1-105">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="f59b1-106">Если вы еще не создали интерфейс Azure API для экземпляра ФХИР в клиенте, ознакомьтесь [со ссылкой краткое руководство: развертывание Azure API для фхир с помощью портала Azure](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="f59b1-106">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="f59b1-107">Щелкните [здесь](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) , чтобы предоставить согласие администратора для приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="f59b1-107">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="f59b1-108">При появлении соответствующего запроса войдите в систему с помощью учетной записи администратора клиента или глобального администратора, а затем нажмите кнопку " **подтвердить** ", чтобы предоставить необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="f59b1-108">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Снимок экрана: запрос разрешения для приложения пациентов](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="f59b1-110">После того как вы согласны, закройте окно.</span><span class="sxs-lookup"><span data-stu-id="f59b1-110">After you accept, close the window.</span></span> <span data-ttu-id="f59b1-111">Вы увидите страницу, которая может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="f59b1-111">You'll see a page that may look like this.</span></span> <span data-ttu-id="f59b1-112">Вы можете пропустить сообщение об ошибке на странице.</span><span class="sxs-lookup"><span data-stu-id="f59b1-112">You can ignore the error message on the page.</span></span> <span data-ttu-id="f59b1-113">Это не так и означает, что разрешение предоставлено.</span><span class="sxs-lookup"><span data-stu-id="f59b1-113">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="f59b1-114">(Мы работаем с более удобной для пользователя страницей для этого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f59b1-114">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="f59b1-115">Оставайтесь на связи!)</span><span class="sxs-lookup"><span data-stu-id="f59b1-115">Stay tuned!)</span></span>

    ![Снимок экрана: запрос разрешения для приложения пациентов](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="f59b1-117">Войдите на [портал Azure](https://portal.azure.com) с учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="f59b1-117">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="f59b1-118">На панели навигации слева выберите пункт **Azure Active Directory**, а затем — **корпоративное приложение**.</span><span class="sxs-lookup"><span data-stu-id="f59b1-118">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="f59b1-119">Найдите строку с именем **пациентов (dev)**, а затем скопируйте значение из СТОЛБЦА " **код объекта** " в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="f59b1-119">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="f59b1-120">![Снимок экрана: строка пациентов (dev) на портале Azure](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="f59b1-120">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="f59b1-121">Перейдите в Azure API для экземпляра ресурса ФХИР, к которому нужно подключить приложение пациентов (путем его поиска или обзора ресурсов), а затем откройте параметры для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f59b1-121">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Снимок экрана: API Azure для параметров экземпляра ФХИР на портале Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="f59b1-123">Нажмите кнопку **Проверка подлинности**, а затем вставьте код объекта, скопированный в действии 3, в поле **Разрешенные идентификаторы объектов** .</span><span class="sxs-lookup"><span data-stu-id="f59b1-123">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="f59b1-124">Это позволяет приложению пациентов получить доступ к серверу ФХИР.</span><span class="sxs-lookup"><span data-stu-id="f59b1-124">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="f59b1-125">После вставки идентификатора объекта Azure Active Directory проверит его, и рядом с ним появится зеленая галочка.</span><span class="sxs-lookup"><span data-stu-id="f59b1-125">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Снимок экрана: параметры проверки подлинности на портале Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="f59b1-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f59b1-127">Click **Save**.</span></span> <span data-ttu-id="f59b1-128">Это повторно развертывает экземпляр, который может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="f59b1-128">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="f59b1-129">Нажмите кнопку **Обзор**и скопируйте URL-адрес из **конечной точки метаданных фхир**.</span><span class="sxs-lookup"><span data-stu-id="f59b1-129">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="f59b1-130">Удалите тег metadata, чтобы получить URL-адрес сервера ФХИР.</span><span class="sxs-lookup"><span data-stu-id="f59b1-130">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="f59b1-131">Например, https://test02-teamshealth.azurehealthcareapis.com/.</span><span class="sxs-lookup"><span data-stu-id="f59b1-131">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Снимок экрана: конечная точка метаданных на портале Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="f59b1-133">В Teams перейдите к экземпляру приложения пациентов, которое загружено в команду, щелкните **Параметры**, а затем в поле **ссылка** введите URL-адрес конечной точки сервера фхир.</span><span class="sxs-lookup"><span data-stu-id="f59b1-133">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="f59b1-134">Затем нажмите кнопку **Подключение** , чтобы установить соединение и найти пациентов в списке.</span><span class="sxs-lookup"><span data-stu-id="f59b1-134">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Снимок экрана: параметры приложения пациентов в Teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="f59b1-136">Если вы получаете сообщение об ошибке при подключении к Teams на этом этапе, отправьте подробный снимок экрана с сообщением об ошибке, журналы из [Fiddler](https://www.telerik.com/download/fiddler) и другие шаги по воспроизводитию в сообщении электронной почты с темой "пациентов App-ЕМР" устранения неполадок "для [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f59b1-136">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f59b1-137">См. также</span><span class="sxs-lookup"><span data-stu-id="f59b1-137">Related topics</span></span>

- [<span data-ttu-id="f59b1-138">Обзор приложения для пациентов</span><span class="sxs-lookup"><span data-stu-id="f59b1-138">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="f59b1-139">Интеграция электронных историй болезни в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f59b1-139">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
