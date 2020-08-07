---
title: Mensagens de alerta de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6819720c-d848-4b90-9b51-89501b4f4645
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d50c3dd24c0057f695a9318c5eef7ad9e7540a45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575653"
---
# <a name="data-alert-messages"></a><span data-ttu-id="7203b-102">Mensagens de alertas de dados</span><span class="sxs-lookup"><span data-stu-id="7203b-102">Data Alert Messages</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="7203b-103">alertas de dados entregam dois tipos de mensagens de alerta de dados por email: mensagens com resultados de alertas de dados e mensagens com descrições de erro.</span><span class="sxs-lookup"><span data-stu-id="7203b-103">data alerts deliver two types of data alert messages by email: Messages with data alert results and messages with error descriptions.</span></span> <span data-ttu-id="7203b-104">As mensagens com resultados mantêm todos os destinatários informados sobre alterações nos dados de relatório que são de interesse comum e importantes para decisões comerciais.</span><span class="sxs-lookup"><span data-stu-id="7203b-104">Messages with results keep all recipients informed about changes in report data that is of common interest and important to business decisions.</span></span> <span data-ttu-id="7203b-105">Se, por alguma razão, ocorrer um erro e os resultados não estiverem disponíveis, a mensagem de erro será enviada.</span><span class="sxs-lookup"><span data-stu-id="7203b-105">If for some reason an error occurs and the results are not available, the error message is sent instead.</span></span>

 <span data-ttu-id="7203b-106">O proprietário da definição de alerta de dados também pode exibir informações sobre a instância de alerta de dados no Gerenciador de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="7203b-106">The owner of the data alert definition also can view information about the data alert instance in Data Alert Manager.</span></span> <span data-ttu-id="7203b-107">Para obter mais informações, consulte [Gerenciador de alertas de dados para os usuários do SharePoint](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span><span class="sxs-lookup"><span data-stu-id="7203b-107">For more information, see [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span></span>

##  <a name="data-alert-messages"></a><a name="DataAlertMessages"></a><span data-ttu-id="7203b-108">Mensagens de alerta de dados</span><span class="sxs-lookup"><span data-stu-id="7203b-108">Data Alert Messages</span></span>
 <span data-ttu-id="7203b-109">As imagens a seguir mostram uma mensagem de alerta de dados com resultados e uma mensagem de alerta com uma descrição de erro.</span><span class="sxs-lookup"><span data-stu-id="7203b-109">The following pictures show a data alert message with results and an alert message with an error description.</span></span>

 <span data-ttu-id="7203b-110">**Mensagem de resultados**</span><span class="sxs-lookup"><span data-stu-id="7203b-110">**Results message**</span></span>

 <span data-ttu-id="7203b-111">![Mensagem de email de alerta de dados com resultados](media/rs-alertmessageresults.gif "Mensagem de email de alerta de dados com resultados")</span><span class="sxs-lookup"><span data-stu-id="7203b-111">![Data alert e-mail message with results](media/rs-alertmessageresults.gif "Data alert e-mail message with results")</span></span>

 <span data-ttu-id="7203b-112">**Mensagem de erro**</span><span class="sxs-lookup"><span data-stu-id="7203b-112">**Error message**</span></span>

 <span data-ttu-id="7203b-113">![Mensagem de alerta de dados com mensagem de erro](media/rs-alertmessageerrror.gif "Mensagem de alerta de dados com mensagem de erro")</span><span class="sxs-lookup"><span data-stu-id="7203b-113">![Data alert message with error message](media/rs-alertmessageerrror.gif "Data alert message with error message")</span></span>

 <span data-ttu-id="7203b-114">As mensagens incluem os mesmos tipos de informações.</span><span class="sxs-lookup"><span data-stu-id="7203b-114">The messages include the same types of information.</span></span>

1.  <span data-ttu-id="7203b-115">**Em nome de** contém o nome da pessoa que criou a definição de alerta de dados.</span><span class="sxs-lookup"><span data-stu-id="7203b-115">**On behalf of** contains the name of the person who created the data alert definition.</span></span>

2.  <span data-ttu-id="7203b-116">Se você forneceu uma descrição na definição de alerta, ela será exibida abaixo de **Em nome de**.</span><span class="sxs-lookup"><span data-stu-id="7203b-116">If you provided a description in the alert definition, it displays below **On behalf of**.</span></span>

3.  <span data-ttu-id="7203b-117">**Resultados de Alerta** exibem as linhas no feed de dados de relatório que satisfazem as regras especificadas na definição de alerta em um formato de tabela ou exibem uma descrição de erro.</span><span class="sxs-lookup"><span data-stu-id="7203b-117">**Alert Results** display the rows in the report data feed that satisfy the rules specified in the alert definition in a tabular format or display an error description.</span></span> <span data-ttu-id="7203b-118">Não há limite para o número de linhas exibidas.</span><span class="sxs-lookup"><span data-stu-id="7203b-118">There is no limit on the number of rows that displays.</span></span>

4.  <span data-ttu-id="7203b-119">**Ir para relatório** é um link para o relatório no qual a definição de alerta se baseia.</span><span class="sxs-lookup"><span data-stu-id="7203b-119">**Go to report** is a link to the report that the alert definition is built upon.</span></span> <span data-ttu-id="7203b-120">Se o link não for válido porque o relatório foi movido ou excluído, uma mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="7203b-120">If the link is not valid because the report was moved or deleted, an error message displays.</span></span>

5.  <span data-ttu-id="7203b-121">**Regra(s)** lista as regras e cláusulas na definição de alerta.</span><span class="sxs-lookup"><span data-stu-id="7203b-121">**Rule(s)** lists the rules and clauses in the alert definition.</span></span> <span data-ttu-id="7203b-122">Essas informações o ajudam a verificar e entender os resultados de alertas e identificar regras na definição de alerta de dados que talvez você queira alterar para limitar ou ampliar os resultados.</span><span class="sxs-lookup"><span data-stu-id="7203b-122">This information helps you verify and understand the alert results and identify rules in the data alert definition that you might want to change to narrow or broaden results.</span></span>

6.  <span data-ttu-id="7203b-123">**Parâmetros de relatório** listam os parâmetros e valores de parâmetros que foram usados quando o relatório foi executado.</span><span class="sxs-lookup"><span data-stu-id="7203b-123">**Report parameters** list the parameters and parameter values that were used when the report was run.</span></span> <span data-ttu-id="7203b-124">Parâmetros e valores de parâmetros o ajudam a entender os resultados de alertas.</span><span class="sxs-lookup"><span data-stu-id="7203b-124">Parameters and parameter values help you understand the alert results.</span></span>

7.  <span data-ttu-id="7203b-125">**Valores Contextuais** listam os nomes e valores de itens de relatório que estão fora das regiões de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="7203b-125">**Contextual values** list the names and values of report items that are outside of the report data regions.</span></span> <span data-ttu-id="7203b-126">Os itens geralmente são caixas de texto.</span><span class="sxs-lookup"><span data-stu-id="7203b-126">The items are typically text boxes.</span></span> <span data-ttu-id="7203b-127">Por exemplo, uma caixa de texto com um valor constante como o assunto ou a descrição de um relatório.</span><span class="sxs-lookup"><span data-stu-id="7203b-127">For example, a text box with a constant value such as the subject or description of a report.</span></span>

 <span data-ttu-id="7203b-128">A única diferença entre os dois tipos de mensagem é o item 5, **Resultados de Alertas**.</span><span class="sxs-lookup"><span data-stu-id="7203b-128">The only difference between the two message types is item 5, **Alert Results**.</span></span> <span data-ttu-id="7203b-129">Se um erro ocorrer quando uma instância de alerta de dados ou mensagem de alerta de dados for criada, a opção **Resultados de Alertas** exibirá uma mensagem de erro que descreve o problema.</span><span class="sxs-lookup"><span data-stu-id="7203b-129">If an error occurs when a data alert instance or data alert message is created, **Alert Results** displays an error message that describes the problem.</span></span> <span data-ttu-id="7203b-130">A mensagem de erro, enviada a todos os destinatários, informa que os resultados de alertas esperados e que podem ser necessários para a tomada de decisões comerciais não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7203b-130">The error message, sent to all recipients, let them know that the alert results that they are expecting and might rely on to make business decisions are not available.</span></span>

 

##  <a name="related-tasks"></a><a name="HowTo"></a> <span data-ttu-id="7203b-131">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="7203b-131">Related Tasks</span></span>
 <span data-ttu-id="7203b-132">Esta seção lista os procedimentos que mostram como criar e editar as definições de alertas de dados que fornecem grande parte das informações exibidas em mensagens de alertas de dados.</span><span class="sxs-lookup"><span data-stu-id="7203b-132">This section lists procedures that show you how to create and edit the data alert definitions that provide much of the information that you see in data alert messages.</span></span>

-   [<span data-ttu-id="7203b-133">Criar um alerta de dados no Designer de alertas de dados</span><span class="sxs-lookup"><span data-stu-id="7203b-133">Create a Data Alert in Data Alert Designer</span></span>](create-a-data-alert-in-data-alert-designer.md)

-   [<span data-ttu-id="7203b-134">Editar um alerta de dados no Designer de alertas</span><span class="sxs-lookup"><span data-stu-id="7203b-134">Edit a Data Alert in Alert Designer</span></span>](edit-a-data-alert-in-alert-designer.md)



## <a name="see-also"></a><span data-ttu-id="7203b-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7203b-135">See Also</span></span>
 <span data-ttu-id="7203b-136">Alertas de dados do [Designer de alertas de dados](../../2014/reporting-services/data-alert-designer.md) [Reporting Services](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7203b-136">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


