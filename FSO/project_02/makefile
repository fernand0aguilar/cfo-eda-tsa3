
# project name (generate executable with this name)
TARGET   = InterProcessCommunication

CC       = gcc

# compiling flags
CFLAGS   =

LINKER   = gcc -o

# linking flags
LFLAGS   = -Wall -I. -lm

# change these to proper directories where each file should be
SRCDIR   = src
LIBDIR	 = lib
OBJDIR   = obj
BINDIR   = bin

SOURCES  := $(wildcard $(SRCDIR)/*.c)
INCLUDES := $(wildcard $(SRCDIR)/*.h)
OBJECTS  := $(SOURCES:$(SRCDIR)/%.c=$(OBJDIR)/%.o)
rm       = rm -f


$(BINDIR)/$(TARGET): $(OBJECTS)
		@$(LINKER) $@ $(LFLAGS) $(OBJECTS)
		@echo "Linking complete!"

$(OBJECTS): $(OBJDIR)/%.o : $(SRCDIR)/%.c
		@$(CC) $(CFLAGS) -c $< -o $@
		@echo "Compiled "$<" successfully!"

.PHONY: clean
clean:
		@$(rm) $(OBJECTS)
		@echo "Cleanup complete!"

.PHONY: remove
remove: clean
		@$(rm) $(BINDIR)/$(TARGET)
		@echo "Executable removed!"

run:
		./$(BINDIR)/$(TARGET)
