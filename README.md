# Dependencies

* python3
* python3-requests
* python3-jinja2
* systemd

# Install

## Current Method

Copy all the systemd service files (`mirrors-index.service`, `mirrors-index.timer`,
`mirrors-index.path`) from `services/` dir into `/etc/systemd/system/`.
Then enable them and start the timer and the path file.

## Previous Method

The following method is obsolete, because /srv/www only contains symlinks.

Add a following line to incrontab:

```/srv/www IN_CREATE,IN_DELETE,IN_MOVE /home/mirror/newindex/genindex.py```

The crontab file was also used to trigger the update based on time before.
Use `crontab -l -u mirror` to check the line that has been commented out for now.

## Locales

Install zh_CN locales since the `genisolist.ini` file contains Chinese characters.

# Copyright

    Copyright © 2013-2016 USTC Linux User Group <lug@ustc.edu.cn>
    All rights reserved.

    This file is part of Mirrors-index.

    Mirrors-index is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License version 2 as
    published by the Free Software Foundation.

    Mirrors-index is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with Mirrors-index.  If not, see <http://www.gnu.org/licenses/>.

* * *
LUG@USTC
