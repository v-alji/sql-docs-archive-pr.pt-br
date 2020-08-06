---
title: Executar um arquivo de script do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], running
ms.assetid: 0de4995c-85ec-4d4c-aaef-fbd30edfb20f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c787d860838a57a2bd0f51aac1e9159833f038d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683370"
---
# <a name="run-a-reporting-services-script-file"></a><span data-ttu-id="ce0bb-102">Executar um arquivo de script do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ce0bb-102">Run a Reporting Services Script File</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ce0bb-103">Os arquivos de script são executados no prompt de comando usando o ambiente de script do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="ce0bb-103">script files are run from the command prompt using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script environment (RS.exe).</span></span> <span data-ttu-id="ce0bb-104">O RS.exe possui diversos argumentos de prompt de comando disponíveis para uso.</span><span class="sxs-lookup"><span data-stu-id="ce0bb-104">RS.exe has many command prompt arguments available for you to use.</span></span> <span data-ttu-id="ce0bb-105">Para obter mais informações sobre as opções de prompt de comando, consulte [Utilitário RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ce0bb-105">For more information about the command prompt options, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span> <span data-ttu-id="ce0bb-106">Para obter mais exemplos de script, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="ce0bb-106">For more script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="sample-command-lines"></a><span data-ttu-id="ce0bb-107">Linhas de Comando de Exemplo</span><span class="sxs-lookup"><span data-stu-id="ce0bb-107">Sample Command Lines</span></span>  
  
-   <span data-ttu-id="ce0bb-108">Execute o Script.rss no ambiente de script designando o servidor de relatório de destino.</span><span class="sxs-lookup"><span data-stu-id="ce0bb-108">Run Script.rss in the script environment designating the target report server.</span></span> <span data-ttu-id="ce0bb-109">O Windows Authentication é aplicado por padrão:</span><span class="sxs-lookup"><span data-stu-id="ce0bb-109">Windows Authentication is applied by default:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver  
    ```  
  
-   <span data-ttu-id="ce0bb-110">Execute o Script.rss no ambiente de script especificando um nome de usuário e senha para autenticar as chamadas de serviço Web:</span><span class="sxs-lookup"><span data-stu-id="ce0bb-110">Run Script.rss in the script environment specifying a user name and password for authenticating the Web service calls:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -u myusername -p mypassword  
    ```  
  
-   <span data-ttu-id="ce0bb-111">Execute o Script.rss no ambiente de script especificando um limite do servidor de 30 segundos:</span><span class="sxs-lookup"><span data-stu-id="ce0bb-111">Run Script.rss in the script environment specifying a server time-out of 30 seconds:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -l 30  
    ```  
  
-   <span data-ttu-id="ce0bb-112">Execute o Script.rss no ambiente de script especificando uma variável de script global chamada *report*.</span><span class="sxs-lookup"><span data-stu-id="ce0bb-112">Run Script.rss in the script environment specifying a global script variable called *report*.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -v report="Company Sales"  
    ```  
  
-   <span data-ttu-id="ce0bb-113">Execute o Script.rss no ambiente de script especificando que as operações de serviço Web no arquivo de script sejam executadas como um lote.</span><span class="sxs-lookup"><span data-stu-id="ce0bb-113">Run Script.rss in the script environment specifying that the Web service operations in the script file are run as a batch.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -b  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ce0bb-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce0bb-114">See Also</span></span>  
 [<span data-ttu-id="ce0bb-115">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ce0bb-115">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
