---
title: 애드온 설치
content_type: concept
weight: 120
---

<!-- overview -->

{{% thirdparty-content %}}

애드온은 쿠버네티스의 기능을 확장한다.

이 페이지는 사용 가능한 일부 애드온과 관련 설치 지침 링크를 나열한다. 이 목차에서 전체를 다루지는 않는다.

<!-- body -->

## 네트워킹과 네트워크 폴리시

* [ACI](https://www.github.com/noironetworks/aci-containers)는 Cisco ACI로 통합 컨테이너 네트워킹 및 네트워크 보안을 제공한다.
* [Antrea](https://antrea.io/)는 레이어 3/4에서 작동하여 쿠버네티스를 위한 네트워킹 및 보안 서비스를 제공하며, Open vSwitch를 네트워킹 데이터 플레인으로 활용한다.
* [Calico](https://docs.projectcalico.org/latest/introduction/)는 네트워킹 및 네트워크 폴리시 제공자이다. Calico는 유연한 네트워킹 옵션을 지원하므로 BGP 유무에 관계없이 비-오버레이 및 오버레이 네트워크를 포함하여 가장 상황에 맞는 옵션을 선택할 수 있다. Calico는 동일한 엔진을 사용하여 서비스 메시 계층(service mesh layer)에서 호스트, 파드 및 (이스티오(istio)와 Envoy를 사용하는 경우) 애플리케이션에 대한 네트워크 폴리시를 적용한다.
* [Canal](https://projectcalico.docs.tigera.io/getting-started/kubernetes/flannel/flannel)은 Flannel과 Calico를 통합하여 네트워킹 및 네트워크 폴리시를 제공한다.
* [Cilium](https://github.com/cilium/cilium)은 네트워킹, 관측 용의성(Observability), 보안 특징을 지닌 eBPF 기반 데이터 플레인을 갖춘 솔루션입니다. Cilium은 기본 라우팅 및 오버레이/캡슐화 모드를 모두 지원하며, 여러 클러스터를 포괄할 수 있는 단순한 플랫(flat) Layer 3 네트워크를 제공합니다. 또한, Cilium은 (네트워크 주소 지정 방식에서 분리된) 신원 기반 보안 모델(identity-based security model)을 사용하여 L3-L7에서 네트워크 정책을 시행할 수 있습니다. Cilium은 kube-proxy를 대체하는 역할을 할 수 있습니다. 또한 부가적으로, 옵트인(opt-in) 형태로 관측 용의성(Observability) 및 보안 기능을 제공합니다.
* [CNI-Genie](https://github.com/cni-genie/CNI-Genie)를 사용하면 쿠버네티스는 Calico, Canal, Flannel, Romana 또는 Weave와 같은 CNI 플러그인을 완벽하게 연결할 수 있다.
* [Contiv](https://contivpp.io/)는 다양한 유스케이스와 풍부한 폴리시 프레임워크를 위해 구성 가능한 네트워킹(BGP를 사용하는 네이티브 L3, vxlan을 사용하는 오버레이, 클래식 L2 그리고 Cisco-SDN/ACI)을 제공한다. Contiv 프로젝트는 완전히 [오픈소스](https://github.com/contiv)이다. [인스톨러](https://github.com/contiv/install)는 kubeadm을 이용하거나, 그렇지 않은 경우에 대해서도 설치 옵션을 모두 제공한다.
* [Contrail](https://www.juniper.net/us/en/products-services/sdn/contrail/contrail-networking/)은 [Tungsten Fabric](https://tungsten.io)을 기반으로 하며, 오픈소스이고, 멀티 클라우드 네트워크 가상화 및 폴리시 관리 플랫폼이다. Contrail과 Tungsten Fabric은 쿠버네티스, OpenShift, OpenStack 및 Mesos와 같은 오케스트레이션 시스템과 통합되어 있으며, 가상 머신, 컨테이너/파드 및 베어 메탈 워크로드에 대한 격리 모드를 제공한다.
* [Flannel](https://github.com/flannel-io/flannel#deploying-flannel-manually)은 쿠버네티스와 함께 사용할 수 있는 오버레이 네트워크 제공자이다.
* [Knitter](https://github.com/ZTE/Knitter/)는 쿠버네티스 파드에서 여러 네트워크 인터페이스를 지원하는 플러그인이다.
* [Multus](https://github.com/k8snetworkplumbingwg/multus-cni)는 쿠버네티스의 다중 네트워크 지원을 위한 멀티 플러그인이며, 모든 CNI 플러그인(예: Calico, Cilium, Contiv, Flannel)과 쿠버네티스 상의 SRIOV, DPDK, OVS-DPDK 및 VPP 기반 워크로드를 지원한다.
* [OVN-Kubernetes](https://github.com/ovn-org/ovn-kubernetes/)는 Open vSwitch(OVS) 프로젝트에서 나온 가상 네트워킹 구현인 [OVN(Open Virtual Network)](https://github.com/ovn-org/ovn/)을 기반으로 하는 쿠버네티스용 네트워킹 제공자이다. OVN-Kubernetes는 OVS 기반 로드 밸런싱과 네트워크 폴리시 구현을 포함하여 쿠버네티스용 오버레이 기반 네트워킹 구현을 제공한다.
* [Nodus](https://github.com/akraino-edge-stack/icn-nodus)는 클라우드 네이티브 기반 서비스 기능 체인(SFC)을 제공하는 OVN 기반 CNI 컨트롤러 플러그인이다.
* [NSX-T](https://docs.vmware.com/en/VMware-NSX-T-Data-Center/index.html) 컨테이너 플러그인(NCP)은 VMware NSX-T와 쿠버네티스와 같은 컨테이너 오케스트레이터 간의 통합은 물론 NSX-T와 PKS(Pivotal 컨테이너 서비스) 및 OpenShift와 같은 컨테이너 기반 CaaS/PaaS 플랫폼 간의 통합을 제공한다.
* [Nuage](https://github.com/nuagenetworks/nuage-kubernetes/blob/v5.1.1-1/docs/kubernetes-1-installation.rst)는 가시성과 보안 모니터링 기능을 통해 쿠버네티스 파드와 비-쿠버네티스 환경 간에 폴리시 기반 네트워킹을 제공하는 SDN 플랫폼이다.
* [Romana](https://github.com/romana)는 [네트워크폴리시 API](/ko/docs/concepts/services-networking/network-policies/)도 지원하는 파드 네트워크용 Layer 3 네트워킹 솔루션이다. 
* [Weave Net](https://github.com/rajch/weave#using-weave-on-kubernetes)은 네트워킹 및 네트워크 폴리시를 제공하고, 네트워크 파티션의 양면에서 작업을 수행하며, 외부 데이터베이스는 필요하지 않다.

## 서비스 검색

* [CoreDNS](https://coredns.io)는 유연하고 확장 가능한 DNS 서버로, 파드를 위한 클러스터 내 DNS로 [설치](https://github.com/coredns/helm)할 수 있다.

## 시각화 &amp; 제어

* [대시보드](https://github.com/kubernetes/dashboard#kubernetes-dashboard)는 쿠버네티스를 위한 대시보드 웹 인터페이스이다.

## 인프라스트럭처

* [KubeVirt](https://kubevirt.io/user-guide/#/installation/installation)는 쿠버네티스에서 가상 머신을 실행하기 위한 애드온이다. 일반적으로 베어 메탈 클러스터에서 실행한다.
* [node problem detector](https://github.com/kubernetes/node-problem-detector)는 
  리눅스 노드에서 실행되며, 
  시스템 이슈를 
  [이벤트](/docs/reference/kubernetes-api/cluster-resources/event-v1/) 또는 
  [노드 컨디션](/ko/docs/concepts/architecture/nodes/#condition) 형태로 보고한다.

## 레거시 애드온

더 이상 사용되지 않는 [cluster/addons](https://git.k8s.io/kubernetes/cluster/addons) 디렉터리에 다른 여러 애드온이 문서화되어 있다.

잘 관리된 것들이 여기에 연결되어 있어야 한다. PR을 환영한다!
