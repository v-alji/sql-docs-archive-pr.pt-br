---
title: Caixa de diálogo Logon do Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 232ee51614a668b07263c3e3a4182f23652135bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683383"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a><span data-ttu-id="1d6f2-102">Caixa de diálogo Logon do Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="1d6f2-102">Reporting Services Login Dialog Box (SSRS)</span></span>
  <span data-ttu-id="1d6f2-103">Use a caixa de diálogo **Logon do Reporting Services** para fornecer credenciais para publicar relatórios no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-103">Use the **Reporting Services Login** dialog box to provide credentials to publish reports to the report server.</span></span>  
  
-   <span data-ttu-id="1d6f2-104">**Observação** Se esta for a primeira vez que você publica um relatório no servidor de relatório desde que você definiu a propriedade de implantação **TargetServerURL** para um projeto, verifique se o nome do servidor especificado é semelhante a `http://localhost/reportserver`e não a `http://localhost/reports`.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-104">**Note** If this is the first time you have published a report to a report server since set you set the deployment property **TargetServerURL** for a project, verify that the server name you specified is similar to `http://localhost/reportserver`, and not `http://localhost/reports`.</span></span> <span data-ttu-id="1d6f2-105">Especificar o diretório `reports` no servidor local em vez do diretório `reportserver` indiretamente faz com que essa caixa de diálogo seja aberta.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-105">Specifying the `reports` directory on the local server instead of the `reportserver` directory indirectly causes this dialog box to open.</span></span> <span data-ttu-id="1d6f2-106">Para obter mais informações sobre como configurar **TargetServerURL**, consulte [Definir as propriedades da implantação &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d6f2-106">For more information about setting **TargetServerURL**, see [Set Deployment Properties &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1d6f2-107">Opções</span><span class="sxs-lookup"><span data-stu-id="1d6f2-107">Options</span></span>  
 <span data-ttu-id="1d6f2-108">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="1d6f2-108">**Server**</span></span>  
 <span data-ttu-id="1d6f2-109">Exibe o nome do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-109">Displays the name of the report server.</span></span> <span data-ttu-id="1d6f2-110">Por exemplo, `http://localhost/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-110">For example, `http://localhost/reportserver`.</span></span> <span data-ttu-id="1d6f2-111">Para servidores de relatório que usam uma porta diferente da porta 80 padrão, inclua o número da porta.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-111">For report servers that use a different port than default port 80, include the port number.</span></span> <span data-ttu-id="1d6f2-112">Por exemplo, `http://localhost:81/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-112">For example, `http://localhost:81/reportserver`.</span></span>  
  
 <span data-ttu-id="1d6f2-113">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="1d6f2-113">**User name**</span></span>  
 <span data-ttu-id="1d6f2-114">Digite o nome de usuário para fazer logon no serviço Web.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-114">Type the user name to log in to the Web service.</span></span>  
  
 <span data-ttu-id="1d6f2-115">**Senha**</span><span class="sxs-lookup"><span data-stu-id="1d6f2-115">**Password**</span></span>  
 <span data-ttu-id="1d6f2-116">Digite a senha para fazer logon no serviço Web.</span><span class="sxs-lookup"><span data-stu-id="1d6f2-116">Type the password to log in to the Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6f2-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d6f2-117">See Also</span></span>  
 <span data-ttu-id="1d6f2-118">[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1d6f2-118">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="1d6f2-119">[Especificar informações de credenciais e de conexão para fontes de dados de relatório](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Report Designer ajuda F1](report-designer-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="1d6f2-119">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Report Designer F1 Help](report-designer-f1-help.md)</span></span>  
  
  
