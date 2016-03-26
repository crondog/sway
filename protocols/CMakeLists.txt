include(Wayland)

WAYLAND_ADD_PROTOCOL_CLIENT(proto-client-xdg-shell
	xdg-shell.xml
	xdg-shell
)
WAYLAND_ADD_PROTOCOL_CLIENT(proto-client-desktop-shell
	desktop-shell.xml
	desktop-shell
)
WAYLAND_ADD_PROTOCOL_SERVER(proto-server-desktop-shell
	desktop-shell.xml
	desktop-shell
)

WAYLAND_ADD_PROTOCOL_CLIENT(proto-client-swaylock
	swaylock.xml
	swaylock
)
WAYLAND_ADD_PROTOCOL_SERVER(proto-server-swaylock
	swaylock.xml
	swaylock
)
WAYLAND_ADD_PROTOCOL_CLIENT(proto-client-dpms
	dpms.xml
	dpms
)
WAYLAND_ADD_PROTOCOL_SERVER(proto-server-dpms
	dpms.xml
	dpms
)

add_library(sway-protocols
	${proto-client-xdg-shell}
	${proto-client-desktop-shell}
	${proto-server-desktop-shell}
	${proto-client-swaylock}
	${proto-server-swaylock}
	${proto-client-dpms}
	${proto-server-dpms}
	)

set(PROTOCOLS_INCLUDE_DIRS ${CMAKE_BINARY_DIR}/protocols PARENT_SCOPE)
