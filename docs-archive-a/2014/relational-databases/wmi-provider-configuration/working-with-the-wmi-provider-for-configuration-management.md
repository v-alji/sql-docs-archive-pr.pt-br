---
title: Trabalhando com o provedor WMI para o gerenciamento de configuração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- permissions [WMI]
- connection strings [WMI]
- security [WMI]
- WMI Provider for Configuration Management, connection strings
- WMI Provider for Configuration Management, security
- late binding [WMI]
- WMI Provider for Configuration Management, late binding
- binding [WMI]
ms.assetid: 34daa922-7074-41d0-9077-042bb18c222a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80f311fb0abae2337f6ea4a5d5d85aaa0d320b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573843"
---
# <a name="working-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="a79a1-102">Trabalhando com o provedor WMI para o Gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="a79a1-102">Working with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="a79a1-103">Considere o seguinte antes de programar com o provedor WMI para Gerenciamento do Computador:</span><span class="sxs-lookup"><span data-stu-id="a79a1-103">Consider the following before programming with the WMI Provider for Computer Management:</span></span>  
  
## <a name="binding"></a><span data-ttu-id="a79a1-104">Associação</span><span class="sxs-lookup"><span data-stu-id="a79a1-104">Binding</span></span>  
 <span data-ttu-id="a79a1-105">O provedor WMI para gerenciamento de configuração é um modelo de objeto COM que dá suporte a associações iniciais e tardias.</span><span class="sxs-lookup"><span data-stu-id="a79a1-105">The WMI Provider for Configuration Management is a COM object model and it supports early and late binding.</span></span> <span data-ttu-id="a79a1-106">Com a associação tardia, você pode usar linguagens de script, como o VBScript, para manipular, de forma programada, os serviços, as configurações de rede e os aliases do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a79a1-106">With late binding you can use script languages, such as VBScript, to manipulate the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and aliases programmatically.</span></span>  
  
 <span data-ttu-id="a79a1-107">Para obter mais informações sobre como programar implementações de provedor WMI usando linguagens de script, consulte o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [site](https://go.microsoft.com/fwlink/?linkid=15426)do MSDN.</span><span class="sxs-lookup"><span data-stu-id="a79a1-107">For further information about programming WMI Provider implementations using scripting languages, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="specifying-a-connection-string"></a><span data-ttu-id="a79a1-108">Especificando uma cadeia de caracteres de conexão</span><span class="sxs-lookup"><span data-stu-id="a79a1-108">Specifying a Connection String</span></span>  
 <span data-ttu-id="a79a1-109">Os aplicativos direcionam o provedor WMI para gerenciamento de configuração para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conectando a um namespace WMI definido pelo provedor.</span><span class="sxs-lookup"><span data-stu-id="a79a1-109">Applications direct the WMI Provider for Configuration Management to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by connecting to a WMI namespace defined by the provider.</span></span> <span data-ttu-id="a79a1-110">O serviço Windows WMI mapeia esse namespace para a DLL do provedor e o carrega na memória.</span><span class="sxs-lookup"><span data-stu-id="a79a1-110">The Windows WMI service maps this namespace to the provider DLL and loads it into memory.</span></span> <span data-ttu-id="a79a1-111">Todas as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são representadas com um único namespace WMI.</span><span class="sxs-lookup"><span data-stu-id="a79a1-111">All instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are represented with a single WMI namespace.</span></span> <span data-ttu-id="a79a1-112">O namespace assume este padrão</span><span class="sxs-lookup"><span data-stu-id="a79a1-112">The namespace defaults to</span></span>  
  
```  
\\.\root\Microsoft\SqlServer\ComputerManagement12\instance_name  
```  
  
 <span data-ttu-id="a79a1-113">onde `instance_name` assume `MSSQLSERVER` como padrão em uma instalação padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a79a1-113">where `instance_name` defaults to `MSSQLSERVER` in a default installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a79a1-114">**Observação:** Se você estiver se conectando por meio do firewall do Windows, precisará verificar se os computadores estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="a79a1-114">**Note:** If you are connecting through Windows Firewall you will need to make sure your computers are configured appropriately.</span></span> <span data-ttu-id="a79a1-115">Consulte o artigo "conectando por meio do firewall do Windows" na documentação do Instrumentação de Gerenciamento do Windows no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [site](https://go.microsoft.com/fwlink/?linkid=15426)do MSDN.</span><span class="sxs-lookup"><span data-stu-id="a79a1-115">See the "Connecting Through Windows Firewall" article in the Windows Management Instrumentation documentation on [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="permissions-and-server-authentication"></a><span data-ttu-id="a79a1-116">Permissões e autenticação do servidor</span><span class="sxs-lookup"><span data-stu-id="a79a1-116">Permissions and Server Authentication</span></span>  
 <span data-ttu-id="a79a1-117">Para acessar o provedor WMI para gerenciamento de configuração, o script de gerenciamento WMI do cliente deve estar sendo executado no contexto de um administrador no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="a79a1-117">To access the WMI Provider for Configuration Management, the client WMI management script must be running in the context of an administrator on the target computer.</span></span> <span data-ttu-id="a79a1-118">Você precisa ser membro do grupo local de administradores do Windows no computador que deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="a79a1-118">You need to be a member of the local Windows administrators group on the computer you want to manage.</span></span>  
  
 <span data-ttu-id="a79a1-119">O administrador pode definir políticas de grupo para controlar o acesso de usuários aos provedores WMI.</span><span class="sxs-lookup"><span data-stu-id="a79a1-119">The administrator can set group policies to control user access to WMI providers.</span></span> <span data-ttu-id="a79a1-120">Para obter mais informações sobre como definir políticas de grupo, consulte "Group Policy and MMC" na ajuda do Gerenciador de Configuração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a79a1-120">For more information about setting group policies see "Group Policy and MMC" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help.</span></span>  
  
 <span data-ttu-id="a79a1-121">O script de gerenciamento WMI pode ser usado para atualizar a conta na qual os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são executados.</span><span class="sxs-lookup"><span data-stu-id="a79a1-121">The WMI management script can be used to update the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services run.</span></span>  
  
 <span data-ttu-id="a79a1-122">Os certificados de segurança são suportados pelo provedor WMI para gerenciamento de configuração.</span><span class="sxs-lookup"><span data-stu-id="a79a1-122">Security certificates are supported by the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="a79a1-123">Para obter mais informações sobre certificados, consulte [hierarquia de criptografia](../security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="a79a1-123">For more information about certificates, see [Encryption Hierarchy](../security/encryption/encryption-hierarchy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a79a1-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a79a1-124">See Also</span></span>  
 [<span data-ttu-id="a79a1-125">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a79a1-125">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
