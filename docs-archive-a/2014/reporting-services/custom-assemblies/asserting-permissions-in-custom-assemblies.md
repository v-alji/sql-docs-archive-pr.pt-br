---
title: Declarando permissões em assemblies personalizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- secure calls [Reporting Services]
- custom assemblies [Reporting Services], permissions
- permission sets [Reporting Services]
- asserting permissions
- permissions [Reporting Services], custom assemblies
- limited permission sets
- security configuration files [Reporting Services]
ms.assetid: 3afb9631-f15e-405e-990b-ee102828f298
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cba3c0b74712b6b4d0f6b5c58925cfd562f0df77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568344"
---
# <a name="asserting-permissions-in-custom-assemblies"></a><span data-ttu-id="eabe1-102">Declarando permissões em assemblies personalizados</span><span class="sxs-lookup"><span data-stu-id="eabe1-102">Asserting Permissions in Custom Assemblies</span></span>
  <span data-ttu-id="eabe1-103">Por padrão, o código de assembly personalizado é executado com o conjunto de permissões limitado **Execução**.</span><span class="sxs-lookup"><span data-stu-id="eabe1-103">By default, custom assembly code runs with the limited **Execution** permission set.</span></span> <span data-ttu-id="eabe1-104">Em alguns casos, talvez você queira implementar um assembly personalizado que crie chamadas seguras para proteger recursos em seu sistema de segurança (como um arquivo ou o Registro).</span><span class="sxs-lookup"><span data-stu-id="eabe1-104">In some cases, you may wish to implement a custom assembly that makes secured calls to protected resources within your security system (such as a file or the registry).</span></span> <span data-ttu-id="eabe1-105">Para realizar isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eabe1-105">In order to accomplish this, you must do the following:</span></span>  
  
1.  <span data-ttu-id="eabe1-106">Identifique as permissões exatas das quais o seu código precisa para fazer a chamada segura.</span><span class="sxs-lookup"><span data-stu-id="eabe1-106">Identify the exact permissions that your code needs in order to make the secured call.</span></span> <span data-ttu-id="eabe1-107">Se esse método fizer parte de uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] biblioteca, essas informações deverão ser incluídas na documentação do método.</span><span class="sxs-lookup"><span data-stu-id="eabe1-107">If this method is part of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] library, this information should be included in the method documentation.</span></span>  
  
2.  <span data-ttu-id="eabe1-108">Modifique os arquivos de configuração de política de servidor de relatório para conceder as permissões exigidas ao assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="eabe1-108">Modify the report server policy configuration files in order to grant the custom assembly the required permissions.</span></span> <span data-ttu-id="eabe1-109">Para obter mais informações sobre os arquivos de configuração da política de segurança, consulte [Usando arquivos da política de segurança do Reporting Services](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span><span class="sxs-lookup"><span data-stu-id="eabe1-109">For more information about the security policy configuration files, see [Using Reporting Services Security Policy Files](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span></span>  
  
3.  <span data-ttu-id="eabe1-110">Declare as permissões exigidas como parte do método no qual a ligação segura será feita.</span><span class="sxs-lookup"><span data-stu-id="eabe1-110">Assert the required permissions as part of the method in which the secure call is made.</span></span> <span data-ttu-id="eabe1-111">Isso é obrigatório porque o código de assembly personalizado chamado pelo servidor de relatório faz parte do assembly host de expressão de relatório, executado com a permissão **Execução** por padrão.</span><span class="sxs-lookup"><span data-stu-id="eabe1-111">This is required because the custom assembly code that is called by the report server is part of the report expression host assembly, which runs with **Execution** permission by default.</span></span> <span data-ttu-id="eabe1-112">O conjunto de permissões **Execução** permite que o código seja executado, mas não permite o uso de recursos protegidos.</span><span class="sxs-lookup"><span data-stu-id="eabe1-112">The **Execution** permission set enables code to run, but not to use protected resources.</span></span>  
  
4.  <span data-ttu-id="eabe1-113">Marque o assembly personalizado com **AllowPartiallyTrustedCallersAttribute** se ele for assinado com um nome forte.</span><span class="sxs-lookup"><span data-stu-id="eabe1-113">Mark the custom assembly with **AllowPartiallyTrustedCallersAttribute** if it is signed with a strong name.</span></span> <span data-ttu-id="eabe1-114">Isso é obrigatório porque os assemblies personalizados são chamados por uma expressão de relatório que faz parte do assembly host de expressão de relatório que, por padrão, não recebe a permissão **FullTrust**; dessa forma, ele é um chamador “parcialmente confiável”.</span><span class="sxs-lookup"><span data-stu-id="eabe1-114">This is required because custom assemblies are called from a report expression that is part of the report expression host assembly, which, by default, is not granted **FullTrust**; thus it is a "partially trusted" caller.</span></span> <span data-ttu-id="eabe1-115">Para obter mais informações, consulte [Usando assemblies de nome forte personalizados](using-strong-named-custom-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="eabe1-115">For more information, see [Using Strong-Named Custom Assemblies](using-strong-named-custom-assemblies.md).</span></span>  
  
## <a name="implementing-a-secure-call"></a><span data-ttu-id="eabe1-116">Implementando uma chamada segura</span><span class="sxs-lookup"><span data-stu-id="eabe1-116">Implementing a Secure Call</span></span>  
 <span data-ttu-id="eabe1-117">Você pode modificar os arquivos de configuração de política para conceder as permissões específicas ao seu assembly.</span><span class="sxs-lookup"><span data-stu-id="eabe1-117">You can modify the policy configuration files to grant your assembly specific permissions.</span></span> <span data-ttu-id="eabe1-118">Por exemplo, se você estiver escrevendo um assembly personalizado para manipular conversão de moedas, talvez seja necessário ler as taxas de câmbio da moeda atual em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="eabe1-118">For example, if you were writing a custom assembly to handle currency conversion, you might need to read the current currency exchange rates from a file.</span></span> <span data-ttu-id="eabe1-119">Para recuperar as informações de taxa, você precisará adicionar outra permissão de segurança, **FileIOPermission**, ao conjunto de permissões do assembly.</span><span class="sxs-lookup"><span data-stu-id="eabe1-119">To retrieve the rate information, you would need to add an additional security permission, **FileIOPermission**, to your permission set for the assembly.</span></span> <span data-ttu-id="eabe1-120">Crie a entrada adicional a seguir no arquivo de configuração de política:</span><span class="sxs-lookup"><span data-stu-id="eabe1-120">You can make the following additional entry in the policy configuration file:</span></span>  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="CurrencyRatesFilePermissionSet"  
   Description="A special permission set that grants read access to my currency rates file.">  
      <IPermission class="FileIOPermission"  
         version="1"  
         Read="C:\CurrencyRates.xml"/>  
      <IPermission class="SecurityPermission"  
         version="1"  
         Flags="Execution, Assertion"/>  
</PermissionSet>  
```  
  
 <span data-ttu-id="eabe1-121">Em seguida, adicione um grupo de códigos que faça referência ao conjunto de permissões:</span><span class="sxs-lookup"><span data-stu-id="eabe1-121">You then add a code group that references that permission set:</span></span>  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="CurrencyRatesFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\MSSQL\Reporting Services\ReportServer\bin\CurrencyConversion.dll"/>  
</CodeGroup>  
```  
  
 <span data-ttu-id="eabe1-122">Para que seu código adquira a permissão apropriada, você deve declarar a permissão em seu código de assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="eabe1-122">In order for your code to acquire the appropriate permission, you must assert the permission within your custom assembly code.</span></span> <span data-ttu-id="eabe1-123">Por exemplo, se quiser adicionar acesso somente leitura a um arquivo XML, C:\CurrencyRates.xml, adicione o código a seguir a seu método:</span><span class="sxs-lookup"><span data-stu-id="eabe1-123">For example, if you want to add read-only access to an XML file, C:\CurrencyRates.xml, you must add the following code to your method:</span></span>  
  
```  
// C#  
FileIOPermission permission = new FileIOPermission(FileIOPermissionAccess.Read, @"C:\CurrencyRates.xml");  
try  
{  
   permission.Assert();  
   // Load the XML currency rates file  
   XmlDocument doc = new XmlDocument();  
   doc.Load(@"C:\CurrencyRates.xml");  
...  
```  
  
 <span data-ttu-id="eabe1-124">Você também pode adicionar a declaraçào como um atributo de método:</span><span class="sxs-lookup"><span data-stu-id="eabe1-124">You can also add the assertion as a method attribute:</span></span>  
  
```  
[FileIOPermissionAttribute(SecurityAction.Assert, Read=@"C:\CurrencyRates.xml")]  
```  
  
 <span data-ttu-id="eabe1-125">Para obter mais informações, consulte "Segurança do .NET Framework" no Guia do desenvolvedor do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eabe1-125">For more information, see ".NET Framework Security" in the .NET Framework Developer's Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabe1-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eabe1-126">See Also</span></span>  
 [<span data-ttu-id="eabe1-127">Usando assemblies personalizados com relatórios</span><span class="sxs-lookup"><span data-stu-id="eabe1-127">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
