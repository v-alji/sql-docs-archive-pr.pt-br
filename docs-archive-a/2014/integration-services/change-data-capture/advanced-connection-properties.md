---
title: Propriedades da Conexão Avançadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4edfab68-7e68-45e8-a3f3-a0049ff7eb9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8dc844d1fdfb1e82f0ffa8de93a6a1060ef190cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575987"
---
# <a name="advanced-connection-properties"></a><span data-ttu-id="fb38b-102">Propriedades Avançadas de Conexão</span><span class="sxs-lookup"><span data-stu-id="fb38b-102">Advanced Connection Properties</span></span>
  <span data-ttu-id="fb38b-103">Use a caixa de diálogo **Propriedades Avançadas de Conexão** para adicionar mais parâmetros de conexão à cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="fb38b-103">Use the **Advanced Connection Properties** dialog box to add more connection parameters to the connection string.</span></span>  
  
 <span data-ttu-id="fb38b-104">Os parâmetros de conexão adicionais podem ser qualquer parâmetro de conexão ODBC que tem suporte pela instância de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando.</span><span class="sxs-lookup"><span data-stu-id="fb38b-104">The additional connection parameters can be any ODBC connection parameter that is supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database instance you are using.</span></span>  
  
 <span data-ttu-id="fb38b-105">Os parâmetros adicionados através da caixa de diálogo **Propriedades Avançadas de Conexão** são adicionados aos parâmetros selecionados usando as opções da caixa de diálogo **Conecte-se ao SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="fb38b-105">The parameters added using the **Advanced Connection Properties** dialog box are added to the parameters selected in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="fb38b-106">A última instância fornecida de cada parâmetro anula qualquer instância anterior do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fb38b-106">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="fb38b-107">Parâmetros adicionados usando a caixa de diálogo **Parâmetros Avançados de Conexão** seguem e substituem os parâmetros fornecidos na caixa de diálogo **Conexão do SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="fb38b-107">Parameters added using the **Advanced Connection Parameters** dialog box follow and replace the parameters provided in the **SQL Server Connection** dialog box.</span></span> <span data-ttu-id="fb38b-108">Por exemplo, se a caixa de diálogo **Conexão do SQL Server** especificar SERVER1 como o Nome do servidor e a página **Parâmetros Adicionais de Conexão** tiver ;SERVER=SERVER2, a conexão será feita ao SERVER2.</span><span class="sxs-lookup"><span data-stu-id="fb38b-108">For example, if the **SQL Server Connection** dialog box specifies SERVER1 as the Server name, and the **Additional Connection Parameters** page contains ;SERVER=SERVER2, the connection will be made to SERVER2.</span></span>  
  
 <span data-ttu-id="fb38b-109">Parâmetros adicionados usando a caixa de diálogo **Propriedades Avançadas de Conexão** sempre são passados como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="fb38b-109">Parameters added using the **Advanced Connection Properties** dialog box are passed as plain text.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb38b-110">Não inclua credenciais de logon na caixa de diálogo **Propriedades Avançadas de Conexão** .</span><span class="sxs-lookup"><span data-stu-id="fb38b-110">Do not include login credentials in the **Advanced Connection Properties** dialog box.</span></span> <span data-ttu-id="fb38b-111">Eles não serão criptografados quando forem transmitidos pela rede.</span><span class="sxs-lookup"><span data-stu-id="fb38b-111">They will not be encrypted when they are passed across the network.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb38b-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb38b-112">See Also</span></span>  
 <span data-ttu-id="fb38b-113">[Acessar o CDC Designer Console](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="fb38b-113">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="fb38b-114">Conexão do SQL Server para a criação de instância</span><span class="sxs-lookup"><span data-stu-id="fb38b-114">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
